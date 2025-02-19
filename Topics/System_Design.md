# Introduction to Distributed Systems

A **distributed system** is a system whose components are located on different networked computers, communicating and coordinating their actions by passing messages. These components (or nodes) can be web servers, databases, or other software programs running on separate machines.


## Key Concepts

### **Concepts**
- **Definition**: A system where components are spread across multiple networked computers.
- **Components**: Nodes (e.g., servers, databases) connected via a network.
- **Communication**: Nodes exchange messages to coordinate actions.
- A **node** is a single computing unit in a distributed system. It can be a physical machine, a virtual machine, or a container running software (e.g., a server, database, or service).

### **Why Use Distributed Systems?**
Distributed systems solve three major problems faced by single-computer systems:

## Parts of a Distributed System
1. **Nodes**: Individual components (e.g., servers, databases) that perform tasks.
2. **Network**: The communication mechanism connecting nodes.


| **Benefit**      | **Problem with Single Computer**                          | **Solution with Distributed Systems**                  |
|-------------------|-----------------------------------------------------------|-------------------------------------------------------|
| **Performance**   | Limited by hardware; expensive to upgrade.                | Use multiple low-spec computers for better performance. |
| **Scalability**   | Cannot handle growing data or traffic beyond a point.     | Distribute data and processing across multiple nodes.  |
| **Availability**  | Single point of failure; cannot guarantee 24/7 uptime.    | Use redundancy to ensure high availability.            |


### **Scaling in Distributed Systems**
- **Vertical Scaling (Scale Up)**:
  - Add more resources (CPU, RAM, storage) to a single node.
  - Limited by the hardware capacity of the node.
- **Horizontal Scaling (Scale Out)**:
  - Add more nodes to the system.
  - Allows for near-limitless scaling by distributing load across nodes.

## Trade-offs in Distributed Systems
While distributed systems offer **performance**, **scalability**, and **availability**, they introduce challenges:
- **Complexity**: Designing and managing distributed systems is harder than single-computer systems.
- **Consistency**: Ensuring data consistency across nodes is difficult.
- **Failure Handling**: Nodes or networks can fail, requiring robust fault tolerance.

---

# Fallacies of Distributed Computing

Developers often make false assumptions when building distributed systems. These fallacies can lead to poor system design and failures. Below is a summary of the key fallacies:

| **Fallacy**                     | **Reality**                                                                 | **Implications**                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **The network is reliable**      | Networks are unreliable; hardware and connections can fail.                 | Design for fault tolerance and retries.                                         |
| **Latency is zero**              | Remote calls have significant latency compared to local memory access.      | Optimize for latency and minimize remote calls.                                 |
| **Bandwidth is infinite**        | Bandwidth is limited, especially over the internet.                        | Optimize data transfer and consider network topology.                           |
| **The network is secure**        | Networks are insecure; data can be intercepted or tampered with.           | Use encryption, authentication, and secure protocols.                          |
| **Topology doesn’t change**      | Network topology changes due to failures or updates.                       | Design for dynamic network conditions.                                          |
| **There is one administrator**   | Networks are managed by multiple entities with different policies.         | Account for varying configurations and policies.                                |
| **The network is homogeneous**   | Networks consist of diverse hardware and software.                         | Ensure compatibility and handle heterogeneity.                                  |
| **Transport cost is zero**       | Data transfer incurs financial and performance costs.                      | Minimize unnecessary data transfer and optimize costs.                          |
| **Global clock fallacy**         | Distributed systems lack a global clock; clocks drift and are inconsistent. | Use logical clocks (e.g., Lamport timestamps) for event ordering.               |

---

# Difficulties in Designing Distributed Systems

Designing distributed systems is challenging due to inherent properties like network asynchrony, partial failures, and concurrency. Below is a summary of these challenges:

| **Challenge**            | **Description**                                                                 | **Implications**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Network Asynchrony**    | Networks cannot guarantee message delivery time, order, or success.             | Messages may be delayed, arrive out of order, or fail to deliver.               |
| **Partial Failures**      | Only some components fail, while others continue to operate.                    | Requires handling atomicity: ensure operations apply to all nodes or none.      |
| **Concurrency**           | Multiple computations occur simultaneously, potentially interfering with each other. | Requires mechanisms to handle race conditions and ensure data consistency.      |

---

# Measures of Correctness in Distributed Systems

Correctness in distributed systems is measured by two key properties: **Safety** and **Liveness**. These properties ensure that a system behaves as expected under all conditions.

| **Property**   | **Definition**                                                                 | **Example (Traffic Light System)**                                                                 |
|----------------|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Safety**     | Something that must **never happen** in a correct system.                     | The traffic light must **never show green for both directions at the same time** (to avoid accidents). |
| **Liveness**   | Something that must **eventually happen** in a correct system.                | The traffic light must **eventually switch from red to green** for each direction (to allow traffic flow). |


## **Notes**
   - There is often a tension between safety and liveness. In some cases, it is impossible to guarantee both simultaneously.
   - Example: In a distributed system, ensuring safety (e.g., no data loss) may delay liveness (e.g., immediate data availability).

---

# System Models in Distributed Systems

Distributed systems can be categorized based on their communication and timing properties. Below is a summary of the key system models:

| **Model**            | **Description**                                                                 | **Key Characteristics**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Synchronous System**| Nodes have accurate clocks and known upper bounds for message delays.           | - Execution is split into rounds. <br> - Nodes run in lock-step. <br> - Easier to reason about. |
| **Asynchronous System**| No fixed upper bounds on message delays or node processing times.              | - Nodes run at independent rates. <br> - No common notion of time. <br> - Closer to real-world systems (e.g., the Internet). |



## **Notes**
1. **Synchronous Systems**:
   - Predictable timing and communication.
   - Easier to design and reason about but less realistic.

2. **Asynchronous Systems**:
   - Unpredictable timing and communication.
   - Harder to design but more representative of real-world distributed systems (e.g., the Internet).

3. **Real-World Relevance**:
   - Most real-world systems (e.g., the Internet) are asynchronous.
