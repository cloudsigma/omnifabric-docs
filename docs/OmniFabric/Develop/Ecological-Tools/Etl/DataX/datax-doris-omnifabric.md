# Write Doris data to OmniFabric using DataX

This article describes how to write Doris data offline to a OmniFabric database using the DataX tool.

## Prepare before you start

Before you can start writing data to OmniFabric using DataX, you need to complete the installation of the following software:

- Finished [installing and starting](../../../../Get-Started/basic-sql.md) OmniFabric.

- Install [JDK 8+ version](https://www.oracle.com/sg/java/technologies/javase/javase8-archive-downloads.html).

- Install [Python 3.8 (or plus)](https://www.python.org/downloads/).

- Download the [DataX](https://datax-opensource.oss-cn-hangzhou.aliyuncs.com/202210/datax.tar.gz) installation package and unzip it.

- Download and install [Doris](https://doris.apache.org/zh-CN/docs/dev/get-starting/quick-start/).

- Download [matrixonewriter.zip](https://community-shared-data-1308875761.cos.ap-beijing.myqcloud.com/artwork/docs/develop/Computing-Engine/datax-write/matrixonewriter.zip) and extract it to the `plugin/writer/` directory in the root of your DataX project.

- Install the <a href="https://dev.mysql.com/downloads/mysql" target="_blank">MySQL Client</a>.

## Steps

### Creating Test Data in Doris

```sql
create database test;

use test;

CREATE TABLE IF NOT EXISTS example_tbl
(
    user_id BIGINT NOT NULL COMMENT "user id",
    date DATE NOT NULL COMMENT "data insertion date time",
    city VARCHAR(20) COMMENT "user city",
    age SMALLINT COMMENT "user age",
    sex TINYINT COMMENT "user gender"
)
DUPLICATE KEY(user_id, date)
DISTRIBUTED BY HASH(user_id) BUCKETS 1
PROPERTIES (
    "replication_num"="1"
);

insert into example_tbl values
(10000,'2017-10-01','Beijing',20,0),
(10000,'2017-10-01','Beijing',20,0),
(10001,'2017-10-01','Beijing',30,1),
(10002,'2017-10-02','Shanghai',20,1),
(10003,'2017-10-02','Guangzhou',32,0),
(10004,'2017-10-01','Shenzhen',35,0),
(10004,'2017-10-03','Shenzhen',35,0);

```

### Creating a Target Library Table in OmniFabric

```sql
create database sparkdemo;
use sparkdemo;

CREATE TABLE IF NOT EXISTS example_tbl
(
    user_id BIGINT NOT NULL COMMENT "user id",
    date DATE NOT NULL COMMENT "data insertion date time",
    city VARCHAR(20) COMMENT "user city",
    age SMALLINT COMMENT "user age",
    sex TINYINT COMMENT "user gender"
);
```

### Edit the json template file for datax

Go to the datax/job path and fill in the following at doris2mo.json

```json
{
  "job": {
    "setting": {
  "speed": {
    "channel": 8
  }
    },
    "content": [
  {
    "reader": {
      "name": "mysqlreader",
      "parameter": {
        "username": "root",
        "password": "root",
        "splitPk": "user_id",
        "column": [
          '*'
        ],
        "connection": [
          {
            "table": [
              "example_tbl"
            ],
            "jdbcUrl": [
              "jdbc:mysql://xx.xx.xx.xx:9030/test"
            ]
          }
        ],
        "fetchSize": 1024
      }
    },
    "writer": {
      "name": "OmniFabricwriter",
      "parameter": {
        "writeMode": "insert",
        "username": "root",
        "password": "111",
        "column": [
          '*'
        ],
        "connection": [
          {
            "jdbcUrl": "jdbc:mysql://xx.xx.xx.xx:6001/sparkdemo",
            "table": [
              "example_tbl"
            ]
          }
        ]
      }
    }
  }
    ]
  }
}
```

### Start the datax job

```bash
python bin/datax.py job/doris2mo.json
```

The following results are displayed:

```bash
2024-04-28 15:47:38.222 [job-0] INFO  JobContainer -
Task Start Time                  : 2024-04-28 15:47:26
Task End Time                    : 2024-04-28 15:47:38
Total Task Time                  :                 11s
Average Task Throughput          :               12B/s
Record Write Speed               :              0rec/s
Total Records Read               :                   7
Total Read/Write Failures        :                   0
```
