# Introduction to Distributed Systems

A **distributed system** is a system whose components are located on different networked computers, communicating and coordinating their actions by passing messages. These components (or nodes) can be web servers, databases, or other software programs running on separate machines.

---

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

---

### **Scaling in Distributed Systems**
- **Vertical Scaling (Scale Up)**:
  - Add more resources (CPU, RAM, storage) to a single node.
  - Limited by the hardware capacity of the node.
- **Horizontal Scaling (Scale Out)**:
  - Add more nodes to the system.
  - Allows for near-limitless scaling by distributing load across nodes.

---

## Trade-offs in Distributed Systems
While distributed systems offer **performance**, **scalability**, and **availability**, they introduce challenges:
- **Complexity**: Designing and managing distributed systems is harder than single-computer systems.
- **Consistency**: Ensuring data consistency across nodes is difficult.
- **Failure Handling**: Nodes or networks can fail, requiring robust fault tolerance.

