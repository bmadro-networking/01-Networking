# Domain C — OSPF / BGP Enterprise Network

Everything uploaded to this folder so far is part of the larger network topology shown in the topology diagram.

This project is built around **OSPF as the internal routing protocol**, with **BGP used between network domains**. VLAN segmentation is used to separate different network functions and user groups.

## BGP & Route Control

Due to limitations in how **Packet Tracer handles prefix filtering and ACL behaviour**, standard prefix filtering and access-list configurations do not consistently behave as intended in this topology.

As a workaround, I control which internal networks are advertised into BGP by selectively redistributing OSPF routes into BGP.

This allows me to control which VLAN networks are exposed across the BGP boundary.

In the current design, **VLAN 10 is the only VLAN permitted to traverse the upper portion of the topology through BGP and reach the networks containing VLAN 30 and VLAN 114 (Leadership).**

This provides a controlled routing boundary between the different parts of the topology while working within the limitations of Packet Tracer.

---

# Changes — 24.09.2026

I deployed **two Layer 3 switches**, shown inside the grey section of the topology.

The L3 switches currently provide DHCP pools for their directly connected networks:

- VLAN 11
- VLAN 12
- VLAN 13
- VLAN 14

This was implemented to remove the bottleneck present in the previous design, where routing and DHCP services were more heavily concentrated on the routers.

The L3 switches participate in **OSPF Area 0**, integrating them directly into the backbone network shown in the light blue section of the topology.

Further work is planned to introduce additional redundancy and develop a more resilient **mesh-based topology**, reducing dependency on individual devices and links.

---

# Changes — 28.09.2026

The main topology of what I consider **Domain C** has been redesigned.

Domain C currently consists of:

- VLAN 11
- VLAN 12
- VLAN 13
- VLAN 14

The two L3 switches continue to provide DHCP services for their respective VLANs as a temporary implementation.

I have also added multiple servers to the topology. These are intended to operate as network services within Domain C and communicate with the rest of the domain through the **OSPF routing infrastructure**.

The topology is therefore moving toward a more complete enterprise-style environment containing:

- VLAN segmentation
- Inter-VLAN routing
- OSPF
- BGP
- DHCP
- Layer 3 switching
- Server infrastructure
- Route redistribution
- Controlled inter-domain reachability
- Planned link and device redundancy

---

# Current Limitations

The primary limitation at this stage is the **physical interface capacity of the Cisco 2911 routers available in Packet Tracer**, combined with the hardware and protocol limitations of the simulator.

The current design contains a **single point of failure** in the connection between Domain C and the wider Core OSPF network.

I am fully aware of this limitation.

Rather than making major changes to the established **Core OSPF Area 0**, I deliberately kept the core architecture largely unchanged while developing Domain C around it.

This allows the domain to be expanded and tested without unnecessarily disrupting the existing OSPF infrastructure.

The intended next stage is to remove this single point of failure by introducing additional physical paths and developing redundancy between the L3 switches and the OSPF core.

---

# Current Status

### Implemented

- OSPF Area 0
- BGP inter-domain routing
- Controlled OSPF → BGP route redistribution
- VLAN segmentation
- Two Layer 3 switches
- DHCP pools on the L3 switches
- VLANs 11–14
- Server infrastructure
- Domain C integration with the OSPF core

### Planned

- Additional redundant paths
- Mesh/redundant topology
- Removal of the current single point of failure
- Further refinement of inter-domain route filtering
- Continued development of the Domain C infrastructure
- Uploading the updated device configurations

> **Note:** The updated device configurations for the 28.09.2026 topology have **not yet been uploaded** to the repository.

---

# Design Philosophy

This topology is being developed incrementally rather than rebuilt from scratch whenever a limitation is encountered.

The objective is to create a realistic enterprise network while documenting the design decisions, limitations, and solutions encountered during development.

Where Packet Tracer prevents a technically preferred implementation from behaving correctly, the limitation is documented and an alternative approach is implemented where practical.

The long-term goal is to evolve the topology toward a **redundant, multi-domain enterprise network** with OSPF, BGP, VLAN segmentation, Layer 3 switching, DHCP, server infrastructure, route filtering, and resilient routing paths.
