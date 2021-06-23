# Notes of _Designing Data-Intensive Applications_

## Table of Contents

### Part I. Foundations of Data Systems

1. [Reliable, Scalable, and Maintainable Applications](Chapter01.md)
    1. Thinking About Data Systems
    2. Reliability
        1. Hardware Faults
        2. Software Errors
        3. Human Errors
        4. How Important Is Reliability?
    3. Scalability
        1. Describing Load
        2. Describing Performance
        3. Approaches for Coping with Load
    4. Maintainability
        1. Operability: Making Life Easy for Operations
        2. Simplicity: Managing Complexity
        3. Evolvability: Making Change Easy
2. [Data Models and Query Languages](Chapter02.md)
    1. Relational Model Versus Document Model
        1. The Birth of NoSQL
        2. The Object-Relational Mismatch
        3. Many-to-One and Many-to-Many Relationships
        4. Are Document Databases Repeating History?
        5. Relational Versus Document Databases Today
    2. Query Languages for Data
        1. Declarative Queries on the Web
        2. MapReduce Querying
    3. Graph-Like Data Models
        1. Property Graphs
        2. The Cypher Query Language
        3. Graph Queries in SQL
        4. Triple-Stores and SPARQL
        5. The Foundation: Datalog
3. [Storage and Retrieval](Chapter03.md)
    1. Data Structures That Power Your Database
        1. Hash Indexes
        2. SSTables and LSM-Trees
        3. B-Trees
        4. Comparing B-Trees and LSM-Trees
        5. Other Indexing Structures
    2. Transaction Processing or Analytics?
        1. Data Warehousing
        2. Stars and Snowflakes: Schemas for Analytics
    3. Column-Oriented Storage
        1. Column Compression
        2. Sort Order in Column Storage
        3. Writing to Column-Oriented Storage
        4. Aggregation: Data Cubes and Materialized Views
4. [Encoding and Evolution](Chapter04.md)
    1. Formats for Encoding Data
        1. Language-Specific Formats
        2. JSON, XML, and Binary Variants
        3. Thrift and Protocol Buffers
        4. Avro
        5. The Merits of Schemas
    2. Modes of Dataflow
        1. Dataflow Through Databases
        2. Dataflow Through Services: REST and RPC
        3. Message-Passing Dataflow

### Part II. Distributed Data

5. [Replication](Chapter05.md)
    1. Leaders and Followers
        1. Synchronous Versus Asynchronous Replication
        2. Setting Up New Followers
        3. Handling Node Outages
        4. Implementation of Replication Logs
    2. Problems with Replication Lag
        1. Reading Your Own Writes
        2. Monotonic Reads
        3. Consistent Prefix Reads
        4. Solutions for Replication Lag
    3. Multi-Leader Replication
        1. Use Cases for Multi-Leader Replication
        2. Handling Write Conflicts
        3. Multi-Leader Replication Topologies
    4. Leaderless Replication
        1. Writing to the Database When a Node Is Down
        2. Limitations of Quorum Consistency
        3. Sloppy Quorums and Hinted Handoff
        4. Detecting Concurrent Writes
6. [Partitioning](Chapter06.md)
    1. Partitioning and Replication
    2. Partitioning of Key-Value Data
        1. Partitioning by Key Range
        2. Partitioning by Hash of Key
        3. Skewed Workloads and Relieving Hot Spots
    3. Partitioning and Secondary Indexes
        1. Partitioning Secondary Indexes by Document
        2. Partitioning Secondary Indexes by Term
    4. Rebalancing Partitions
        1. Strategies for Rebalancing
        2. Operations: Automatic or Manual Rebalancing
    5. Request Routing
        1. Parallel Query Execution
7. [Transactions](Chapter07.md)
    1. The Slippery Concept of a Transaction
        1. The Meaning of ACID
        2. Single-Object and Multi-Object Operations
    2. Weak Isolation Levels
        1. Read Committed
        2. Snapshot Isolation and Repeatable Read
        3. Preventing Lost Updates
        4. Write Skew and Phantoms
    3. Serializability
        1. Actual Serial Execution
        2. Two-Phase Locking (2PL)
        3. Serializable Snapshot Isolation (SSI)
8. [The Trouble with Distributed Systems](Chapter08.md)
    1. Faults and Partial Failures
        1. Cloud Computing and Supercomputing
    2. Unreliable Networks
        1. Network Faults in Practice
        2. Detecting Faults
        3. Timeouts and Unbounded Delays
        4. Synchronous Versus Asynchronous Networks
    3. Unreliable Clocks
        1. Monotonic Versus Time-of-Day Clocks
        2. Clock Synchronization and Accuracy
        3. Relying on Synchronized Clocks
        4. Process Pauses
    3. Knowledge, Truth, and Lies
        1. The Truth Is Defined by the Majority
        2. Byzantine Faults
        3. System Model and Reality
9. [Consistency and Consensus](Chapter09.md)
    1. Consistency Guarantees
    2. Linearizability
        1. What Makes a System Linearizable?
        2. Relying on Linearizability
        3. Implementing Linearizable Systems
        4. The Cost of Linearizability
    3. Ordering Guarantees
        1. Ordering and Causality
        2. Sequence Number Ordering
        3. Total Order Broadcast
    4. Distributed Transactions and Consensus
        1. Atomic Commit and Two-Phase Commit (2PC)
        2. Distributed Transactions in Practice
        3. Fault-Tolerant Consensus
        4. Membership and Coordination Services

### Part III. Derived Data

10. [Batch Processing](Chapter10.md)
    1. Batch Processing with Unix Tools
        1. Simple Log Analysis
        2. The Unix Philosophy
    2. MapReduce and Distributed Filesystems
        1. MapReduce Job Execution
        2. Reduce-Side Joins and Grouping
        3. Map-Side Joins
        4. The Output of Batch Workflows
        5. Comparing Hadoop to Distributed Databases
    3. Beyond MapReduce
        1. Materialization of Intermediate State
        2. Graphs and Iterative Processing
        3. High-Level APIs and Languages
11. [Stream Processing](Chapter11.md)
    1. Transmitting Event Streams
        1. Messaging Systems
        2. Partitioned Logs
    2. Databases and Streams
        1. Keeping Systems in Sync
        2. Change Data Capture
        3. Event Sourcing
        4. State, Streams, and Immutability
    3. Processing Streams
        1. Uses of Stream Processing
        2. Reasoning About Time
        3. Stream Joins
        4. Fault Tolerance
12. [The Future of Data Systems](Chapter12.md)
    1. Data Integration
        1. Combining Specialized Tools by Deriving Data
        2. Batch and Stream Processing
    2. Unbundling Databases
        1. Composing Data Storage Technologies
        2. Designing Applications Around Dataflow
        3. Observing Derived State
    3. Aiming for Correctness
        1. The End-to-End Argument for Databases
        2. Enforcing Constraints
        3. Timeliness and Integrity
        4. Trust, but Verify
    3. Doing the Right Thing
        1. Predictive Analytics
        2. Privacy and Tracking
