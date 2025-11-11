# Victoria University – Enterprise LAN (Cisco Packet Tracer)

## Overview
Multi-building campus LAN with per-department segmentation, inter-VLAN routing on L3 switches, EtherChannel, FHRP, and NAT at the enterprise edge to the ISP.

## Architecture
- Buildings: A, G, K, L, M (K = core/server building)
- Departments: Sport, Health, Business, Engineering, HR
- Segmentation: VLAN-per-department, SVIs on L3 switches
- Redundancy: EtherChannel (L2 bundling), FHRP for gateway resiliency
- Edge: Single gateway router → ISP, NAT overload

## IP Plan
- Internal supernet: 172.XY.0.0/16 (VLSM)
- ISP link: 200.1.X.0/24
- Tables for each VLAN/subnet with SVI GW, range, broadcast

## Config Highlights
- L2: vlan/trunking, channel-group
- L3: interface vlan, ip routing, fhrp (hsrp/vrrp/glbp)
- Edge: ip nat inside/outside, overload, default route

## Validation
- End-to-end pings across VLANs and to ISP
- show vlan brief | show etherchannel summary | show standby/vrrp | show ip route | show ip nat translations
- Simulated L3 switch failure → traffic continuity verified

## Files
- final.pkt
