## 1. System Overview

The infrastructure consists of a primary compute node (Jumpertech EZBook S5), an administrative machine (Lenovo ThinkPad Yoga 11e), and supporting devices used for constrained connectivity, storage, and remote access.

The environment operates under hardware and connectivity limitations, including unreliable internal storage and non-functional wireless networking on the primary node. System design is therefore adapted around externalized storage and alternative network pathways.



## 2. Compute Node Setup

- Installed Arch Linux minimal TS on Jumpertech EZBook S5
- System configured as primary infrastructure execution node
- External SSD enclosure used as primary storage medium due to unreliable internal SSD detection
- System verified as bootable and operational under external storage dependency

![[Snapshot_2026-05-23_00-19-54.png]]



## 3. Network Connectivity

- Internet access provided via Oppo A3S USB tethering (LTE uplink)
- Primary node lacks usable built-in WiFi/Bluetooth connectivity
- Network environment relies on DHCP-assigned dynamic addressing via mobile gateway

Result:
- Internet connectivity achieved through mobile tethering under constrained network conditions

![[Snapshot_2026-05-23_00-23-26.png]]



## 4. Remote Access Setup

- Tailscale deployed on both administrative and infrastructure machines
- Stable device-to-device connectivity established through identity-based overlay network
- SSH access operates over Tailscale virtual network instead of local network addressing

Result:
- Reliable remote administration achieved despite dynamic IP assignment and NAT constraints introduced by mobile tethering

![[Snapshot_2026-05-23_00-19-54.png]]



## 5. Storage Configuration

- Internal M.2 SSD identified as unreliable for consistent system boot and operation
- External SSD enclosure implemented as primary system storage layer
- System operation restructured to depend on external storage device

Result:
- Stable storage operation achieved under hardware-level storage constraints

![[Snapshot_2026-05-23_00-23-26.png]]



## 6. Key Build Decisions

- Hardware limitations accepted and mitigated rather than replaced
- External storage used as primary persistence layer
- Mobile device used as sole network uplink provider
- Remote access implemented via overlay networking instead of direct LAN dependency
- System design prioritized operational continuity over ideal hardware configuration



## 7. Current Build Outcome

The system is operational under constrained conditions with the following capabilities:

- functional Linux-based compute node
- stable remote access via Tailscale overlay network
- working internet connectivity via mobile LTE tethering
- operational external storage-based system configuration



## 8. Build Summary

Phase 2 establishes a working infrastructure environment under significant hardware and networking constraints. The system demonstrates practical implementation of constrained system deployment, alternative networking strategies, and hardware failure mitigation through externalized components and overlay networking.