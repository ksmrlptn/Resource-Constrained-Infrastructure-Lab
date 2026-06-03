# 1. Project Overview

## Objective
The Resource-Constrained Infrastructure Lab (RCIL) is a personal infrastructure project created to develop practical IT Support, Systems Administration, and infrastructure troubleshooting skills using limited and repurposed hardware.

The environment is designed to provide hands-on experience with real-world infrastructure and operational challenges under constrained conditions, including aging hardware, unstable components, limited storage flexibility, and budget limitations.

Rather than focusing on enterprise-scale deployment, the project emphasizes:
- infrastructure planning
- system configuration
- troubleshooting
- operational documentation
- recovery procedures
- constraint-based decision making

The project serves as both:
- a hands-on learning environment
- a portfolio demonstrating practical infrastructure and operational thinking

## Scope
The project includes:
- physical hardware inventory and role assignment
- network planning and connectivity
- system deployment and configuration
- storage management
- operational procedures
- incident tracking and troubleshooting
- infrastructure documentation and evidence collection

## Current Status
The infrastructure has completed initial deployment and baseline operational setup. Core system functionality, remote access capability, and constrained-network connectivity have been successfully established.



# 2. Constraints

## Hardware Constraints
- primary systems rely on aging or consumer-grade hardware
- limited CPU performance and memory capacity
- storage devices may have reliability issues or limited lifespan
- no dedicated enterprise-grade server hardware

## Financial Constraints
- no budget for enterprise infrastructure or cloud services
- project relies on existing and reused equipment

## Design Impact
These constraints enforce a design approach focused on:
- simplicity over scalability
- reliability over complexity
- recovery over redundancy



# 3. Asset Inventory

| Asset                            | Type       | Specs | Intended Role                                 | Status    |
| -------------------------------- | ---------- | ----- | --------------------------------------------- | --------- |
| Lenovo ThinkPad Yoga 11e 3rd Gen | Laptop     | TBD   | Main administration / documentation system    | Available |
| Jumpertech EZBook S5             | Laptop     | TBD   | Primary infrastructure node (lab system host) | Available |
| D-Link DWR-M960 LTE              | Router     | TBD   | Reserved network gateway (not yet in use)     | Available |
| Oppo A3S                         | Mobile     | TBD   | Monitoring / access / network bridge          | Available |
| DTGC-C M.2 2280 SATA 128GB       | Storage    | TBD   | Primary storage candidate (under validation)  | Available |
| USB to NVMe/SATA SSD Enclosure   | Peripheral | TBD   | External storage interface / recovery layer   | Available |
| USB Hub                          | Peripheral | TBD   | Device expansion / connectivity support       | Available |
| USB Flash Drive                  | Storage    | TBD   | Boot media / recovery / transfer tool         | Available |



# 4. Infrastructure Roles

## Main Laptop (Lenovo ThinkPad Yoga 11e 3rd Gen)
- Role: Administrative System
- Purpose: Documentation, configuration management, and control interface

## Jumpertech EZBook S5
- Role: Primary infrastructure node
- Purpose: Main system for OS installation, services, and lab environment execution

## D-Link DWR-M960 LTE Router
- Role: Reserved network gateway
- Purpose: Intended future internet access and local network management
- Status: Not currently integrated into system

## DTGC-C M.2 2280 SATA 128GB
- Role: Primary storage candidate
- Purpose: OS installation target (under validation due to hardware instability risk)

## USB to NVMe/SATA Enclosure  
- Role: External storage interface  
- Purpose: Boot/recovery storage and fallback system disk  

## USB Flash Drive  
- Role: Boot and recovery media  
- Purpose: OS installation and system recovery  

## USB Hub  
- Role: Expansion interface  
- Purpose: Peripheral connectivity support  

## Oppo A3S  
- Role: Mobile utility device  
- Purpose: Provides internet via USB tethering



# 5. Architecture Overview

## Infrastructure Goal
System functionality is maintained through external workaround solutions due to hardware limitations.

## System Relationships
- Main Laptop acts as administrative and control interface
- Jumpertech EZBook S5 acts as execution node for all infrastructure tasks
- Mobile device provides network bridging via USB tethering (current method)
- External SSD provides storage reliability layer
- Tailscale provides stable remote access layer

## Planned Connectivity
- Administrative access: Main Laptop → Tailscale → Jumpertech Node
- Internet access: Jumpertech Node → Oppo A3S USB tether → LTE network (current method)
- Planned alternative: D-Link router integration for network management (not yet implemented)
- Storage access: Jumpertech Node → External SSD enclosure



# 6. Network Plan

## Planned Network Layout
- Single-node primary compute environment
- External device-based internet bridging
- Mesh overlay network for remote access stability

## IP Planning
- DHCP-based local network allocation
- Tailscale overlay removes dependency on static IP addressing

## Access Methods
- SSH via Tailscale
- Local console access
- Remote administration via main laptop



# 7. Notes

## Observations
- Internal hardware reliability is inconsistent
- External components are required for stable operation
- remote administration currently depends on Tailscale mesh connectivity

## Risks
- Dependency on smartphone tethering for connectivity
- Storage reliability depends on external enclosure

## Future Considerations
- Integration of router for stable network architecture
- Possible hardware upgrades if instability increases