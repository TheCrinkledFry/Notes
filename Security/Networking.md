# Chapter 1: Computer Networks and the Internet

## Section 1

### 1.1.0

> [!IMPORTANT]
>
> When talking about what networking is, this book will teach it using the internet as a reference to it.

When it comes to describing what a network is, there are two ways to do this:

1. _Hardware and Software_: The hardware aspect of this will be things like routers, switches, cabling, network interface cards, etc. When it comes to the software aspect of it this will be things like the operating system, network management software, security software, and protocols, etc.
2. _Network Infrastructure_: This will be things like firewalls, the path of cabling, servers, internet service provider towers, DNS, etc.

### 1.1.1

Each device connected to a network is called a **end system** (or **host**). These words are synonymous of each other.

The way that two different **end systems** communicate with each other is through **communication links** and **packet switches**. When it comes to the **communication links**, there are different types that change how the devices communicate with each other and they are: _coaxial cable_, _copper wire_, _optical cable_, and _radio spectrum_.

When it comes to the different types of **communication links**, each one will transfer data at different rates to the other **end system**. The speed at which the data is sent is called **transmission rate**. There is a way to calculate this with the equation being:

$$
\text{Transmission Rate} = \frac{\text{Total data to send (bits)}}{\text{Maximum data transfer per second (bits/s)}}
$$

When the data is actually now being sent to the receiving **end system**, this will not all be sent in one giant chunk. Instead, the total data to send will be sent in multiple smaller sections. Each of the small sections will contain extra non-related data called _header data_. The _header data_ combined with the actual data is called a **packet**.

> [!NOTE]
>
> For example, a total of 50 bits needs to be sent from system A to system B. The data is sent the **communication link** will only be able to send 15 bits per second. However, since data is split up into multiple parts, each **packet** will be 11 bits of actual data and 4 bits of _header information_ so each packet is 15 bits. This means four **packets** (15, 15, 15, and 9) bits each one. It will take ~ 3.6 seconds to send all 4 packets to the desired **end system**. Once they reach **end system** B they will all be reassembled to make the original 50 bit thing of data.

A **packet switch** and is what takes a **packet** and sends it to its next destination in the transfer of that **packet** to the receiving **end system**. This works by getting received by its _incoming communication link_ and being sent out the _outgoing communication link_. The two most common types of **packet switches** are: _routers_ and _link layer switches_. When it comes to the placement of the two types, the _router_ is more used in the network core while the _link layer switch_ is more used in access networks.

All the **packet switches** that a **packet** had to take to get the the desired **end system** is called a **route** (or **path**).

An **ISP** (**internet service provider**) is a company that is providing internet related services to other **end systems** and deal with the routing of how to send and receive data from one **end system** to the other. An **ISP** can be from telephone companies, Universities, corporates, etc.

When it comes to how the **ISP** will communicate with each other, these will communicate with each other from **upper tier** and **national ISP** providers.

A **network protocol** defines the complete set of mandatory conventions and operating procedures that determine reliable communication between independent **end systems**. These standardized rules dictate every aspect of data exchange to ensure mutual understanding and successful interaction:

- **Syntax and Semantics:** Specifies the necessary format and structure for data to be correctly packaged and interpreted, alongside the type and scope of permissible content within the transmission.
- **Connection Management**: Outlines the precise mechanisms for establishing, maintaining, and terminating a connection between two end systems.
- **Transmission Control**: Establishes the parameters for acceptable transmission speed, data sequencing, and flow control to manage network capacity and prevent congestion.
- **Data Integrity**: Protocols embed procedures for error detection and recovery. These mechanisms are essential for validating data integrity and ensuring that any corruption or loss during transit is identified and addressed.

> [!NOTE]
>
> A good example of a **protocol** is the _TCP/IP_ protocol. This is the common one used for transferring data over the internet.

When it comes to who makes the **protocols** standards, this is done by the _IETF_ (_Internet Engineering Task Force_). The actual documents they make to describe how the **protocol** would work is called _RFC_ (_Request For Commits_).

### 1.1.2

A **distributed system** is comprised of multiple independent computer **end systems** that are physically separate but are interconnected through a network. These systems function cohesively to accomplish a unified, common objective like working a multiplayer game.

The primary benefit of this architecture is **workload distribution** (or **load balancing**), which allows the overall processing demands to be shared across various end systems. This parallel execution effectively mitigates the burden on any **end system**, thereby enhancing performance, scalability, and efficiency. Another thing this provides is **fault tolerance**, meaning if one component fails, the other independent systems can often continue processing, ensuring greater system reliability and availability.

> [!NOTE]
>
> An example of a **distributed system** is purchasing stuff from target. The purchase service might go down, but can still look at the items target has and add stuff to the cart. Even though one part of the overall system failed, the whole thing did not.

A **socket** is a way that two different **end systems** are able to know which specific _application service_ running on the **end system** to send data to. More about this will be talked about later.

> [!IMPORTANT]
>
> An _application service_ is just a process that is running on an **end system**. An example of this is outlook. The outlook is a running process that has a specific **socket** that is tells other **end systems** that wanna send mail to it so send it at that specific **socket**.

## Section 2
