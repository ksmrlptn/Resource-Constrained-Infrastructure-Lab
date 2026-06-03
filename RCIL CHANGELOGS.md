This document tracks all meaningful changes made to the Resource-Constrained Infrastructure Lab (RCIL). It records system evolution, decisions, incidents, and operational improvements.



## [Phase 1] — System Definition

### Summary
Defined the scope of the RCIL environment under hardware and financial constraints. Established the concept of a constrained infrastructure lab using repurposed consumer hardware.

### Key Outputs
- Project structure defined
- Hardware inventory identified
- Constraints documented
- Design philosophy established (simplicity over complexity, recovery over redundancy)



## [Phase 2] — System Building and Initial Deployment

### Summary
Initial system deployment on Jumpertech EZBook S5 with Arch Linux minimal installation and external storage dependency.

### Key Changes
- Installed Arch Linux on primary compute node
- Configured external SSD as primary storage layer due to unreliable internal disk behavior
- Established mobile-based internet connectivity via Oppo A3S USB tethering
- Implemented Tailscale for stable remote access across NAT-restricted network
- Established ThinkPad as administrative control machine

### Outcome
Functional infrastructure node achieved under constrained hardware conditions.



## [Phase 3] — System Maintenance (Back ups & Recoveries)

| MAINTENANCE |                   |                                                                               |
| :---------: | :---------------: | :---------------------------------------------------------------------------: |
|   REC-001   | RCIL Sys Recovery | Implemented manual backup system for system recovery and reinstall scenarios. |
|             |                   |                                                                               |



## [Phase 4] — System Maintenance Troubleshooting

| INCIDENTS |                                                            |                                                                    |
| :-------: | :--------------------------------------------------------: | :----------------------------------------------------------------: |
|  INC-001  |                  Input Device Degradation                  | Shift administration to remote access via Tailscale using Thinkpad |
|  INC-002  |               Internal SSD Detection Failure               |                External SSD-based system deployment                |
|  INC-003  |             Native Wireless Connectivity Loss              |              USB tethering via Oppo A3S mobile device              |
|  INC-004  | Mobile-Tethered Network Environment Unstable Remote Access | Deploy Tailscale across administrative and infrastructure systems  |
|           |                                                            |                                                                    |



## [Phase 5] — System Improvements

| IMPROVEMENTS |                                        |                                                    |
| :----------: | :------------------------------------: | :------------------------------------------------: |
|   IMP-001    | Stable Remote Monitoring Architechture | Established glances to monitor jumpertech remotely |



## Current State
The RCIL environment is operational with:
- functional compute node
- external storage dependency model
- mobile-based internet access
- remote administration via Tailscale
- initial recovery system in place