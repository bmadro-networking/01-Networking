Everything I have uploaded so far is part of the topology you can find in this folder.

Normal Pre-fix and accesslists do not work as intended in packet tracer, so I have to allow the VLANs of my choosing free access thru BGP, which I monitor by choosing which Networks to redistribute from OSPF to BGP.

Whats not seen in this topology is that VLAN 10 is the only vlan allowed from the upper part of the topology, through BGP to reach VLANs 30, and vlan 114 (Leadership).

CHANGES MADE 24.09.2026

I deployed two L3-switches as seen in the grey box, these currently also carry the respective DHCP-pools for their connected networks VLAN 11, 12 and VLAN 13 and 14. This was to eliminate bottlenecking in the earlier state of this network. The L3-switches are operating with OSPF and are part of AREA 0 as seen in the light blue box. Further work needs to be done to create redundancy by developing MESH networks. 
