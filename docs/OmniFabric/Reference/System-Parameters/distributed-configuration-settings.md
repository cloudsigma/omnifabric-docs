# Distributed Common Parameters Configuration

In the *OmniFabric/etc/launch-with-proxy/* directory, there are four configuration files: *cn.toml*, *tn.toml*, *proxy.toml*, and *log.toml*. The parameters contained in these configuration files are explained below:

---

## cn.toml

### Default Parameters

| Parameter          | Explanation                                                                                                                             | Example                     |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| [log]              | Log configuration section                                                                                                               |                             |
| level              | Log level; default is `info`.                                                                                                           | level = "info"              |
| [cn]               | `cn` node, not editable                                                                                                                 | /                           |
| port-base          | Starting port used by `cn`. It scans the next 20 ports from this base to find available ones for internal services.                     | port-base = 18000           |
| service-host       | Service connection address used for registration with HAKeeper                                                                           | service-host = "127.0.0.1"  |
| [cn.frontend]      | Frontend configuration section                                                                                                          |                             |
| port               | Listening port for OmniFabric and client connections                                                                                     | port = 6001                 |
| host               | Listening IP address                                                                                                                     | host = "0.0.0.0"            |
| [fileservice.s3]   | S3 file service configuration                                                                                                            |                             |
| bucket             | S3 bucket name                                                                                                                           | bucket = "my-bucket"        |
| key-prefix         | S3 key prefix                                                                                                                            | key-prefix = "prefix/"      |

### Extended Parameters

| Parameter               | Explanation                                                                                                                                                                                                                                     | Example                         |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
| [log]                   | Log configuration section                                                                                                                                                                                                                        |                                 |
| format                  | Log save format (e.g., `console`, `json`)                                                                                                                                                                                                       | format = "console"              |
| filename                | Log filename                                                                                                                                                                                                                                     | filename = "log1.log"           |
| [cn.frontend]           | Frontend configuration section                                                                                                                                                                                                                   |                                 |
| unix-socket             | Listen on Unix domain socket                                                                                                                                                                                                                     | unix-socket = "/tmp/mysql.sock" |
| lengthOfQueryPrinted    | Console output query length                                                                                                                                                                                                                      | lengthOfQueryPrinted = 200000   |
| enableTls               | Enable TLS                                                                                                                                                                                                                                       | enableTls = false               |
| tlsCaFile               | Client SSL CA list file path                                                                                                                                                                                                                     | tlsCaFile = ""                  |
| tlsCertFile             | Client X509 PEM format certificate file path                                                                                                                                                                                                     | tlsCertFile = ""                |
| tlsKeyFile              | Client X509 PEM format key file path                                                                                                                                                                                                             | tlsKeyFile = ""                 |
| saveQueryResult         | Save query results                                                                                                                                                                                                                               | saveQueryResult = false         |
| queryResultTimeout      | Query result timeout (hours)                                                                                                                                                                                                                     | queryResultTimeout = 24         |
| queryResultMaxsize      | Maximum query result size (MB)                                                                                                                                                                                                                   | queryResultMaxsize = 100        |
| lowerCaseTableNames     | Case sensitivity of identifiers; default `1` = case-insensitive                                                                                                                                            | lowerCaseTableNames = 1         |
| [cn.Txn]                | Transaction configuration section                                                                                                                                                                                                                |                                 |
| isolation               | Transaction isolation level on the `cn` node. If not set: with `mode=optimistic` → Serializable Isolation (SI); with `mode=pessimistic` → Read Committed (RC). Default: RC                                                                      | isolation = "RC"                |
| mode                    | Transaction mode (`optimistic` / `pessimistic`). Default: `pessimistic`.                                                                                                                                                                         | mode = "pessimistic"            |
| [fileservice.s3]        | Additional S3 options                                                                                                                                                                                                                             |                                 |
| endpoint                | S3 endpoint address                                                                                                                                                                                                                               | endpoint = "s3.amazonaws.com"   |
| [fileservice.cache]     | File service cache configuration                                                                                                                                                                                                                  |                                 |
| memory-capacity         | Cache memory size                                                                                                                                                                                                                                 | memory-capacity = "512MB"       |
| disk-path               | Disk cache path                                                                                                                                                                                                                                   | disk-path = "/var/OmniFabric/cache" |
| disk-capacity           | Disk cache capacity                                                                                                                                                                                                                               | disk-capacity = "8GB"           |
| [observability]         | Observability parameters                                                                                                                                                                                                                          |                                 |
| host                    | Exposed metrics service listening IP                                                                                                                                                                                                              | host = "0.0.0.0"                |
| statusPort              | Prometheus monitoring port; metrics exposed via HTTP                                                                                                                                                                                              | statusPort = 7001               |
| enableMetricToProm      | Enable metric service                                                                                                                                                                                                                             | enableMetricToProm = false      |
| disableMetric           | Disable metric collection and stop listening on service port                                                                                                                                                                                      | disableMetric = false           |
| disableTrace            | Disable trace collection (also stops collecting metric and log data)                                                                                                                                                                              | disableTrace = false            |
| longQueryTime           | Threshold (seconds) for logging long queries; `0.0` = log all execution plans                                                                                                                                                                     | longQueryTime = 1.0             |

---

## tn.toml

### Default Parameters

| Parameter        | Explanation                                                                                                                                     | Example                                   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| [log]            | Log configuration section                                                                                                                       |                                           |
| level            | Log level; default is `info`                                                                                                                    | level = "info"                            |
| [dn]             | TN node, not editable                                                                                                                           |                                           |
| uuid             | Unique identifier of TN, not editable                                                                                                           | uuid = "dd4dccb4-4d3c-41f8-b482-5251dc7a41bf" |
| port-base        | Starting port used by `TN`. It scans the next 20 ports from this base to find available ones for internal services.                             | port-base = 19000                         |
| service-host     | Service connection address used for registration with HAKeeper                                                                                  | service-host = "0.0.0.0"                  |
| [fileservice.s3] | S3 file service configuration                                                                                                                   |                                           |
| bucket           | S3 bucket name                                                                                                                                  | bucket = "my-bucket"                      |
| key-prefix       | S3 key prefix                                                                                                                                   | key-prefix = "prefix/"                    |

### Extended Parameters

| Parameter             | Explanation                                                                                          | Example                           |
|-----------------------|------------------------------------------------------------------------------------------------------|-----------------------------------|
| [log]                 | Log configuration section                                                                            |                                   |
| format                | Log save format (e.g., `console`, `json`)                                                            | format = "console"                |
| filename              | Log filename                                                                                         | filename = "log1.log"             |
| [dn.LogtailServer]    | Logtail server configuration section                                                                  |                                   |
| rpc-enable-checksum   | Enable RPC checksum                                                                                  | rpc-enable-checksum = false       |
| [fileservice.s3]      | Additional S3 options                                                                                |                                   |
| endpoint              | S3 endpoint address                                                                                  | endpoint = "s3.amazonaws.com"     |
| [fileservice.cache]   | File service cache configuration                                                                      |                                   |
| memory-capacity       | Cache memory size                                                                                    | memory-capacity = "512MB"         |
| disk-path             | Disk cache path                                                                                      | disk-path = "/var/OmniFabric/cache" |
| disk-capacity         | Disk cache capacity                                                                                  | disk-capacity = "8GB"             |
| [observability]       | Observability parameters                                                                             |                                   |
| host                  | Exposed metrics service listening IP                                                                  | host = "0.0.0.0"                  |
| statusPort            | Prometheus monitoring port; metrics exposed via HTTP                                                  | statusPort = 7001                 |
| enableMetricToProm    | Enable metric service                                                                                 | enableMetricToProm = false        |
| disableMetric         | Disable metric collection and stop listening on service port                                          | disableMetric = false             |
| disableTrace          | Disable trace collection (also stops collecting metric and log data)                                  | disableTrace = false              |
| longQueryTime         | Threshold (seconds) for logging long queries; `0.0` = log all execution plans                         | longQueryTime = 1.0               |

---

## log.toml

### Default Parameters

| Parameter          | Explanation                                 | Example                                   |
|--------------------|---------------------------------------------|-------------------------------------------|
| [log]              | Log configuration section                   |                                           |
| level              | Log level; default is `info`                | level = "info"                            |
| [logservice]       | Logservice configuration section            |                                           |
| uuid               | Unique identifier of Logservice, not editable | uuid = "dd1dccb4-4d3c-41f8-b482-5251dc7a41bf" |
| data-dir           | Default data directory                       | data-dir = "./mo-data/logservice"         |
| [fileservice.s3]   | S3 file service configuration                |                                           |
| bucket             | S3 bucket name                               | bucket = "my-bucket"                      |
| key-prefix         | S3 key prefix                                | key-prefix = "prefix/"                    |

### Extended Parameters

| Parameter                      | Explanation                                                                                          | Example                       |
|--------------------------------|------------------------------------------------------------------------------------------------------|-------------------------------|
| [log]                          | Log configuration section                                                                            |                               |
| format                         | Log save format (e.g., `console`, `json`)                                                            | format = "console"            |
| filename                       | Log filename                                                                                         | filename = "log1.log"         |
| [logservice.BootstrapConfig]   | Logservice bootstrap configuration                                                                    |                               |
| num-of-log-shards              | Number of log shards                                                                                 | num-of-log-shards = 0         |
| num-of-tn-shards               | Number of TN shards                                                                                  | num-of-tn-shards = 0          |
| num-of-log-shard-replicas      | Replicas per log shard                                                                               | num-of-log-shard-replicas = 0 |
| [fileservice.s3]               | Additional S3 options                                                                                |                               |
| endpoint                       | S3 endpoint address                                                                                  | endpoint = "s3.amazonaws.com" |
| [fileservice.cache]            | File service cache configuration                                                                      |                               |
| memory-capacity                | Cache memory size                                                                                    | memory-capacity = "512MB"     |
| disk-path                      | Disk cache path                                                                                      | disk-path = "/var/OmniFabric/cache" |
| disk-capacity                  | Disk cache capacity                                                                                  | disk-capacity = "8GB"         |
| [observability]                | Observability parameters                                                                             |                               |
| host                           | Exposed metrics service listening IP                                                                  | host = "0.0.0.0"              |
| statusPort                     | Prometheus monitoring port; metrics exposed via HTTP                                                  | statusPort = 7001             |
| enableMetricToProm            | Enable metric service                                                                                 | enableMetricToProm = false    |
| disableMetric                  | Disable metric collection and stop listening on service port                                          | disableMetric = false         |
| disableTrace                   | Disable trace collection (also stops collecting metric and log data)                                  | disableTrace = false          |
| longQueryTime                  | Threshold (seconds) for logging long queries; `0.0` = log all execution plans                         | longQueryTime = 1.0           |

---

## proxy.toml

### Default Parameters

| Parameter          | Explanation                                | Example                      |
|--------------------|--------------------------------------------|------------------------------|
| [log]              | Log configuration section                  |                              |
| level              | Log level; default is `info`               | level = "info"               |
| [proxy]            | Proxy configuration section                |                              |
| listen-address     | Listen address; default `0.0.0.0:6009`     | listen-address = "0.0.0.0:6009" |
| [fileservice.s3]   | S3 file service configuration              |                              |
| bucket             | S3 bucket name                              | bucket = "my-bucket"         |
| key-prefix         | S3 key prefix                               | key-prefix = "prefix/"       |

### Extended Parameters

| Parameter            | Explanation                                                                                                                                                                                                                   | Example                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| [log]                | Log configuration section                                                                                                                                                                                                      |                               |
| format               | Log save format (e.g., `console`, `json`)                                                                                                                                                                                      | format = "console"            |
| filename             | Log filename                                                                                                                                                                                                                   | filename = "log1.log"         |
| [proxy]              | Proxy configuration section                                                                                                                                                                                                    |                               |
| rebalance-interval   | Time interval between two rebalance operations (load balancing)                                                                                                                                                                | rebalance-interval = 30       |
| rebalance-disabled   | Disable rebalance; if `true`, no automatic rebalancing                                                                                                                                                                         | rebalance-disabled = false    |
| rebalance-tolerance  | Rebalance tolerance `< 1`. Example: `0.3` → trigger rebalance if a server exceeds average connections by 30%.                                                                                                                 | rebalance-tolerance = 0.3     |
| [fileservice.s3]     | Additional S3 options                                                                                                                                                                                                          |                               |
| endpoint             | S3 endpoint address                                                                                                                                                                                                            | endpoint = "s3.amazonaws.com" |
| [fileservice.cache]  | File service cache configuration                                                                                                                                                                                               |                               |
| memory-capacity      | Cache memory size                                                                                                                                                                                                              | memory-capacity = "512MB"     |
| disk-path            | Disk cache path                                                                                                                                                                                                                | disk-path = "/var/OmniFabric/cache" |
| disk-capacity        | Disk cache capacity                                                                                                                                                                                                            | disk-capacity = "8GB"         |
| [observability]      | Observability parameters                                                                                                                                                                                                        |                               |
| host                 | Exposed metrics service listening IP                                                                                                                                                                                           | host = "0.0.0.0"              |
| statusPort           | Prometheus monitoring port; metrics exposed via HTTP                                                                                                                                                                           | statusPort = 7001             |
| enableMetricToProm   | Enable metric service                                                                                                                                                                                                          | enableMetricToProm = false    |
| disableMetric        | Disable metric collection and stop listening on service port                                                                                                                                                                   | disableMetric = false         |
| disableTrace         | Disable trace collection (also stops collecting metric and log data)                                                                                                                                                           | disableTrace = false          |
| longQueryTime        | Threshold (seconds) for logging long queries; `0.0` = log all execution plans                                                                                                                                                  | longQueryTime = 1.0           |