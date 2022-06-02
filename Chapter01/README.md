# Introduction

- [Introduction](#introduction)
  - [Architectural Principles](#architectural-principles)
    - [Packets, Connections, and Datagrams](#packets-connections-and-datagrams)
    - [The End-to-End Argument and Fate Sharing](#the-end-to-end-argument-and-fate-sharing)

When a *set of common behaviors* is used with a *common language*, a **protocol** is being used.

A *collection* of related protocols is called a **protocol suite**.

The design that specifies **how** various protocols of a *protocol suite* relate to each other and divide up tasks to be accomplished is called the **architecture** or **reference model** for the *protocol suite*.

**TCP/IP** is a *protocol* suite that implements the **Internet architecture** and draws its origins from the `ARPANET1` *Reference Model* (ARM) `[RFC0871]`.

It is worth mentioning that the TCP/IP architecture evolved from work that addressed a need to **provide interconnection** of multiple **different** *packet-switched* computer networks.
> This was accomplished using a set of **gateways** (later called **routers**).

## Architectural Principles

The *TCP/IP protocol suite* allows computers, smartphones, and embedded devices of all sizes, supplied from many **different** computer vendors and running totally **different** software, to **communicate** with each other.

It is truly an **open system** in that the *definition* of the protocol suite and many of its implementations are **publicly** available at little or no charge.

It forms the basis for what is called the *global Internet, or the **Internet**, a wide area network (WAN) of about two billion users that literally spans the globe.

**Internet architecture** should be able to *interconnect* multiple **distinct** networks and that multiple activities should be able to run **simultaneously** on the resulting interconnected network.

### Packets, Connections, and Datagrams

One of the important concepts developed in the 1960s (e.g., in [B64]) was the idea of **packet switching**.

In **packet switching**, *chunks* (*packets*) of digital information comprising some number of bytes are carried through the network somewhat **independently**.
> Chunks coming from different sources or senders can be *mixed together* and *pulled apart* later, which is called **multiplexing**.  
> The chunks can be moved around from one switch to another on their way to a destination, and the path might be subject to change.

This has two potential advantages:

1. The network can be more resilient.
2. There can be better utilization of the network links and switches because of **statistical multiplexing**.

When packets are received at a packet switch, they are ordinarily stored in **buffer memory** or **queue** and processed in a *first-come-first-served* (FCFS) fashion.  
This is the simplest method for scheduling the way packets are processed and is also called *first-in-first-out* (FIFO).

In **statistical multiplexing**, traffic is mixed together based on the arrival statistics or timing pattern of the traffic.

Such multiplexing is simple and efficient, because:

- If there is any network capacity to be used and traffic to use it, the network will be busy (high utilization) at every bottleneck or choke point.

The downside of this approach is:

- Limited predictability.
  > the performance seen by any particular application depends on the statistics of other applications that are sharing the network.

Alternative techniques, such as **time-division multiplexing** (TDM) and **static multiplexing**, typically *reserve* a certain amount of *time* or *other resources* for data on each connection.

> Although such techniques can lead to more predictability, a feature useful for supporting constant bit rate telephone calls, they may not fully utilize the network capacity because reserved bandwidth may go **unused**.

The **VC** (virtual circuit) abstraction and **connection-oriented** packet networks required some information or **state** to be stored in each switch for each connection.

- The reason is that each packet carries only a **small** bit of overhead information that provides an index into a **state table**.

**Connection-oriented** network is related to the system which supports connection establishment, clearing, and status information.

A a **datagram** is a special type of packet in which all the identifying information of the *source* and *final destination* resides inside the **packet itself**.
> (instead of in the packet switches).

Although this tends to require **larger** packets, per-connection state at packet switches is no longer required and a **connectionless** network could be built, eliminating the need for a (complicated) signaling protocol.

One other related concept is that of **message boundaries** or **record markers**.

when an application sends more than one chunk of information into the network, the fact that more than one chunk was written may or may not be preserved by the communication protocol.  
Most datagram protocols preserve **message boundaries**.

### The End-to-End Argument and Fate Sharing
