# Introduction

- [Introduction](#introduction)
  - [Architectural Principles](#architectural-principles)
    - [Packets, Connections, and Datagrams](#packets-connections-and-datagrams)

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
