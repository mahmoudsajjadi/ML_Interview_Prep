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

