# Standalone Common Parameters Configuration

Four configuration files are in the *OmniFabric/etc/launch/* directory: *cn.toml*, *tn.toml*, *proxy.toml*, and *log.toml*, used to configure standard parameters.

---

## cn.toml

### Default Parameters

| Parameter      | Explanation                                                                 | Example                  |
|----------------|-----------------------------------------------------------------------------|--------------------------|
| [log]          | Log configuration section                                                   |                          |
| level          | Log level, default is info. Can be modified to different levels.            | level = "info"           |
| [cn]           | cn node, not editable                                                       | /                        |
| port-base      | Starting port number. "cn" finds 20 available ports starting from this base | port-base = 18000        |
| service-host   | Service connection address used for registration to HAKeeper                | service-host = "127.0.0.1" |
| [cn.frontend]  | Frontend configuration section                                              |                          |
| port           | Port for OmniFabric to listen and for client connections                    | port = 6001              |
| host           | Listening IP address                                                        | host = "0.0.0.0"         |

### Extended Parameters

| Parameter           | Explanation                                                                                       | Example                   |
|---------------------|---------------------------------------------------------------------------------------------------|---------------------------|
| [log]               | Log configuration section                                                                         |                           |
| format              | Log save format (console, JSON, etc.)                                                             | format = "console"        |
| filename            | Log filename                                                                                      | filename = "mo.log"       |
| [cn.frontend]       | Frontend configuration section                                                                    |                           |
| unix-socket         | Listen to Unix domain interface                                                                   | unix-socket = "/tmp/mysql.sock" |
| lengthOfQueryPrinted| Console output query length                                                                       | lengthOfQueryPrinted = 200000 |
| enableTls           | Enable TLS                                                                                        | enableTls = false         |
| tlsCaFile           | Client SSL CA list file path                                                                      | tlsCaFile = ""            |
| tlsCertFile         | Client X509 PEM format cert file path                                                             | tlsCertFile = ""          |
| tlsKeyFile          | Client X509 PEM format key file path                                                              | tlsKeyFile = ""           |
| saveQueryResult     | Save query results                                                                                | saveQueryResult = false   |
| queryResultTimeout  | Query result timeout (hours)                                                                      | queryResultTimeout = 24   |
| queryResultMaxsize  | Query result maximum size (MB)                                                                    | queryResultMaxsize = 100  |
| lowerCaseTableNames | Identifier case sensitivity. Default = 1 (case insensitive).                                      | lowerCaseTableNames = 1   |
| [cn.Txn]            | Transaction configuration section                                                                 |                           |
| isolation           | Transaction isolation level (e.g. RC, SI). Default: RC                                            | isolation = "RC"          |
| mode                | Transaction mode (optimistic/pessimistic). Default: optimistic                                    | mode = "optimistic"       |
| [fileservice.cache] | File service cache configuration section                                                          |                           |
| memory-capacity     | Cache memory size                                                                                 | memory-capacity = "512MB" |
| [observability]     | Observability parameters                                                                          |                           |
| host                | Exposed metrics service listening IP                                                              | host = "0.0.0.0"          |
| statusPort          | Prometheus monitoring port                                                                        | statusPort = 7001         |
| enableMetricToProm  | Enable metric service                                                                             | enableMetricToProm = false|
| disableMetric       | Disable metric collection                                                                         | disableMetric = false     |
| disableTrace        | Disable trace collection                                                                          | disableTrace = false      |
| longQueryTime       | Threshold (seconds) for logging long queries. 0.0 = log all                                       | longQueryTime = 1.0       |

---

## tn.toml

### Default Parameters

| Parameter      | Explanation                                                                 | Example                  |
|----------------|-----------------------------------------------------------------------------|--------------------------|
| [log]          | Log configuration section                                                   |                          |
| level          | Log level, default is info. Can be modified                                 | level = "info"           |
| [dn]           | TN node, not editable                                                       |                          |
| uuid           | Unique identifier of TN, not editable                                       | uuid = "dd4dccb4-4d3c-41f8-b482-5251dc7a41bf" |
| port-base      | Starting port number. "TN" finds 20 available ports starting from this base | port-base = 19000        |
| service-host   | Service connection address used for registration to HAKeeper                | service-host = "0.0.0.0" |

### Extended Parameters

| Parameter          | Explanation                                                                                      | Example                   |
|--------------------|--------------------------------------------------------------------------------------------------|---------------------------|
| [log]              | Log configuration section                                                                        |                           |
| format             | Log save format (console, JSON, etc.)                                                            | format = "console"        |
| filename           | Log filename                                                                                     | filename = "tn.log"       |
| [dn.LogtailServer] | Logtail Server configuration section                                                             |                           |
| rpc-enable-checksum| Enable RPC checksum                                                                              | rpc-enable-checksum = false|
| [fileservice.cache]| File service cache configuration section                                                         |                           |
| memory-capacity    | Cache memory size                                                                                | memory-capacity = "512MB" |
| [observability]    | Observability parameters                                                                         |                           |
| host               | Exposed metrics service listening IP                                                             | host = "0.0.0.0"          |
| statusPort         | Prometheus monitoring port                                                                       | statusPort = 7001         |
| enableMetricToProm | Enable metric service                                                                            | enableMetricToProm = false|
| disableMetric      | Disable metric collection                                                                        | disableMetric = false     |
| disableTrace       | Disable trace collection                                                                         | disableTrace = false      |
| longQueryTime      | Threshold (seconds) for logging long queries. 0.0 = log all                                      | longQueryTime = 1.0       |

---

## log.toml

### Default Parameters

| Parameter      | Explanation                                                   | Example                  |
|----------------|---------------------------------------------------------------|--------------------------|
| [log]          | Log configuration section                                     |                          |
| level          | Log level, default is info. Can be modified                   | level = "info"           |
| [logservice]   | Logservice configuration section                              |                          |
| uuid           | Unique identifier of Logservice, not editable                 | uuid = "dd1dccb4-4d3c-41f8-b482-5251dc7a41bf" |
| data-dir       | Default data directory                                        | data-dir = "./mo-data"   |

### Extended Parameters

| Parameter                | Explanation                                                                                | Example                   |
|---------------------------|--------------------------------------------------------------------------------------------|---------------------------|
| [log]                    | Log configuration section                                                                  |                           |
| format                   | Log save format (console, JSON, etc.)                                                      | format = "console"        |
| filename                 | Log filename                                                                               | filename = "log1.log"     |
| [logservice]             | Logservice configuration section                                                           |                           |
| logservice-address       | Logservice address                                                                         | logservice-address = "0.0.0.0:32000" |
| raft-address             | Raft address                                                                               | raft-address = "0.0.0.0:32001" |
| gossip-address           | Gossip address                                                                             | gossip-address = "0.0.0.0:32002" |
| gossip-seed-addresses    | Gossip seed node addresses                                                                 | gossip-seed-addresses = "" |
| [LogtailServer.BootstrapConfig] | LogtailServer bootstrap configuration section                                       |                           |
| init-hakeeper-members    | Initial HAKeeper members                                                                   | init-hakeeper-members = "" |
| [fileservice.cache]      | File service cache configuration section                                                   |                           |
| memory-capacity          | Cache memory size                                                                          | memory-capacity = "512MB" |
| [observability]          | Observability parameters                                                                   |                           |
| host                     | Exposed metrics service listening IP                                                       | host = "0.0.0.0"          |
| statusPort               | Prometheus monitoring port                                                                 | statusPort = 7001         |
| enableMetricToProm       | Enable metric service                                                                      | enableMetricToProm = false|
| disableMetric            | Disable metric collection                                                                  | disableMetric = false     |
| disableTrace             | Disable trace collection                                                                   | disableTrace = false      |
| longQueryTime            | Threshold (seconds) for logging long queries. 0.0 = log all                                | longQueryTime = 1.0       |

---

## proxy.toml

### Default Parameters

| Parameter      | Explanation                                                   | Example                  |
|----------------|---------------------------------------------------------------|--------------------------|
| [log]          | Log configuration section                                     |                          |
| level          | Log level, default is info. Can be modified                   | level = "info"           |
| [proxy]        | Proxy configuration section                                   |                          |
| listen-address | Proxy listen address, default is `0.0.0.0:6009`               | listen-address = "0.0.0.0:6009" |

### Extended Parameters

| Parameter           | Explanation                                                                                          | Example                   |
|---------------------|------------------------------------------------------------------------------------------------------|---------------------------|
| [log]               | Log configuration section                                                                            |                           |
| format              | Log save format (console, JSON, etc.)                                                                | format = "console"        |
| filename            | Log filename                                                                                         | filename = "proxy.log"    |
| [proxy]             | Proxy configuration section                                                                          |                           |
| rebalance-interval  | Time interval between two rebalance operations (load balancing).                                     | rebalance-interval = 30   |
| rebalance-disabled  | Disable rebalance. If true, rebalance operations will not occur.                                     | rebalance-disabled = false|
| rebalance-tolerance | Tolerance for rebalance. Value < 1. Ex: 0.3 = rebalance triggers if server exceeds +30% average load | rebalance-tolerance = 0.3 |
| [fileservice.cache] | File service cache configuration section                                                             |                           |
| memory-capacity     | Cache memory size                                                                                    | memory-capacity = "512MB" |
| [observability]     | Observability parameters                                                                             |                           |
| host                | Exposed metrics service listening IP                                                                 | host = "0.0.0.0"          |
| statusPort          | Prometheus monitoring port                                                                           | statusPort = 7001         |
| enableMetricToProm  | Enable metric service                                                                                | enableMetricToProm = false|
| disableMetric       | Disable metric collection                                                                            | disableMetric = false     |
| disableTrace        | Disable trace collection                                                                             | disableTrace = false      |
| longQueryTime       | Threshold (seconds) for logging long queries. 0.0 = log all                                          | longQueryTime = 1.0       |