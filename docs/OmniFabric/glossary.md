# **Glossary**

### **Terms**

It's helpful to understand a few terms before reading our architecture documentation.

|  Term   | Definition   |
|  ----  | ----  |
| A  |  |
| AST (Abstract syntax tree)  | Abstract Syntax Trees or ASTs are tree representations of code. They are a fundamental part of the way a compiler works. |
| C  |  |
| Cluster  | A distributed OmniFabric deployment, which acts as a single logical application.|
| E  |  |
  | Explicit Transactions| Explicit Transaction has the beginning, ending and rollback of transactions with the command Begin Transaction, Commit Transaction and Rollback Transaction. |
  |I|  |
  | Implicit Transactions| Implicit Transaction is the auto commit. There is no beginning or ending of the transaction. |
  |O||
  |Optimistic transaction| Optimistic transaction, the optimistic transaction means that when the transaction starts, no conflict detection or lock will be performed, the current relevant data will be cached in the corresponding memory area, and the data will be added, deleted, or modified. |
  |P||
  |Pessimistic transaction|Pessimistic transaction, the default transaction mode of OmniFabric, that is, when the transaction starts, it will assume that the transaction-related tables are in a state where write conflicts will occur and lock the corresponding data table or a data row in advance to complete the locking action Finally, the insertion, modification, or deletion of data is cached in memory. After committing or rolling back, the data is placed on the disk, and the lock is released. |
  | S  |  |
  | Snapshot Isolation (SI) | Snapshot Isolation is a multi-version concurrency control approach that is widely used in practice. OmniFabric supports distributed transaction of snapshot isolation level. |

### **Concepts**

OmniFabric relies heavily on the following concepts. Being familiar with them will help you understand what our architecture achieves.

|  Term   | Definition   |
|  ----  | ----  |
| A  |  |
| Auto-Rebalance  | A modern distributed database should do more than just split data amongst a number of servers. The automatic process of storage and workload distribution among servers is called an Auto-Rebalance. |
| C  |  |
| Consistency  | OmniFabric supports a strong consistency. It is guaranted that after any successful data write, the reading afterwards will get the latest value, no matter from which store. |
| E  |  |
| Execution Plan  | An execution plan in a database is a simple graphical representation of the operations that the query optimizer generates to calculate the most efficient way to return a set of results.  |
| F  |  |
| Fault-Tolerance  | Fault-Tolerance simply means a system's ability to continue operating uninterrupted despite the failure of one or more of its components.  |
| M  |  |
| Monolithic Engine  | A monolithic database engine is designed to support hybrid workloads: transactional, analytical, streaming, time-series, machine learning, and so on.  |
| Materialized View  | A materialized view is a pre-computed data set derived from a query specification (the SELECT in the view definition) and stored for later use. Materialized view is usually used for increasing performance and efficiency. |
| Metadata  | Metadata is the data that describes the structure and creation method of data in a database. |
| P  |  |
| Paxos  | Paxos is an algorithm that is used to achieve consensus among a distributed set of computers that communicate via an asynchronous network. |
| R  |  |
| Raft  | Raft is a consensus algorithm that is designed to be easy to understand. It's equivalent to Paxos in fault-tolerance and performance. The difference is that it's decomposed into relatively independent subproblems, and it cleanly addresses all major pieces needed for practical systems. |
| Raft Group and Leader | Raft defines a strong, single leader and number of followers in a group of peers. The group represents a replicated state machine. Only the leader may service client requests. The leader replicates actions to the followers. |
 | S  |  |
  | SIMD instruction | SIMD is short for Single Instruction/Multiple Data, while the term SIMD operations refers to a computing method that enables processing of multiple data with a single instruction. |
| T  |  |
| Transaction | A set of operations performed on your database that satisfy the requirements of ACID semantics. |
|TAE| Transactional Analytic Engine. The storage engine is the main public interface of the storage layer, which can support both row and column storage and transaction processing capabilities. |
| V  |  |
| Vectorized Execution  | Vectorized data processing helps with developing faster analytical query engines by making efficient utilization of CPU cache. Arrow's columnar format allows to use lightweight schemes like dictionary encoding, bit packing, and run length encoding, which favor query performance over compression ratio. |
