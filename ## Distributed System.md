## Distributed System

A distributed system is a collection of seperate and independernt software/hardware components, called nodes, that are networked and work together coherently by coordincating and communicating through messages passing or events, to fulfill one end goal.

Nodes can be unstructure or highly structured, depending on the system requirements. The complexities are hidden away from the end user, making the whole system appear as one computer.

### Characteristics

1. No shared clock. order evenets - logical clock is achieved through coordination
2. No shared memory. state is distributed throughout the system
3. Concurrency. tasks are executed concurrently
4. Heterogeneity and Loose Coupling. (optional) different OS and technologies

Distributed systems are usually

- Dynamic
- Overlay Networks

Examples: Paas, Iaas, Serverless, etc.

### Basic Concepts

Nodes have their own processors and could be hardware/software, forming open or
closed groups.

Resource is an asset that's accessed remotely. It could be virutally anything, such as files, services, storage, other networks, etc.

Distribution Transparency is to keep as much of the system as hidden as possible, from the user. This is done through a middleware.

Middleware is a logical layer on top of the collective nodes. It handles communication, security, failures, etc. It can be though of as the backbone of the system.

Concurrency is the parallel completion of multiple tasks and operations. It is an intrinsic property of distributed systems.

Coordination is the smooth collaboration between operations and events.
Synchronzaion orders and controls resource sharing.

The Architectural Model:

- Arrangement of Nodes
- Structure of system
- Interaction and communication between nodes
- Provides: Mangement of complexity and ease of maintenance

Global State:

- The union of the states of seperate processes
- Overview of the entire system
- Equivalent of a global namespace or object that holds all global variables

### Common Motives

1. Concensus
   - Online Banking
   - Bidding Platform
2. Resource Sharing
   - Distributed Databases
   - Distributed File Systems
   - Example: BitTorrent
3. Data replication
4. Horizontal Scalability
5. Availability

### Types of Distributed System

1. Coupling and Scale
   1. Cluster Computing
      - Homogenous
      - Management is centralized
      - Used for high perfomance and minimum downtime
   2. Grid Computing
      - Heterogenous and geographically dispersed
      - Management is decentralized
      - Used for large repository of data and high computing power
2. Architecture Model
   1. Layered
      Nodes are grouped into seperate layers, each with a specific goal, e.g. Client-Server Model
   2. Object-Based
      Nodes are loosely coupled with synchronous communication that can make direct calls to other nodes.
   3. Data-centered
      The system is based around a primary data centre through which the nodes communicate.
   4. Event-based
      Nodes communicate and perform operations through their reaction to events.

### Advantages

1. Reliability
2. Scalability
3. Fault Tolerance
4. Increased Performance

### Disadvantages

1. Difficult to detect failures
2. Performance bottlenecks
3. Redundancy
4. Inconsistency

### Issues and Considerations

Assumptions made by developers which lead to pitfalls:

1. Zero latency
2. Network is secure and reliable
3. Topotlogy won't change

The most important principle that is followed is: The Design for Failure
