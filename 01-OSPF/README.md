# OSPF

This section contains the OSPF portion of a larger, self-designed enterprise network.

The environment is divided into multiple OSPF areas, with Area 0 operating as the backbone and additional areas connected through Area Border Routers (ABRs). The topology is designed to explore multi-area OSPF, redundant routing paths, inter-area connectivity, and network convergence.

The lab includes:

- Multi-area OSPF (Areas 0–3)
- OSPF backbone and ABR design
- Redundant routing paths
- Inter-area routing
- Router and link failure testing
- Route convergence and troubleshooting
- Integration with external networks through BGP

The topologies shown here are sections of the larger network rather than isolated labs. Some OSPF networks operate within the same domain, while others connect to separate domains through BGP tunnels.

Both Packet Tracer and GNS3 are used throughout the project. GNS3 is used where a more realistic or less restricted environment is required.

See [`05-Images`](../05-Images) for the complete network topology and the relationship between the different network sections.
