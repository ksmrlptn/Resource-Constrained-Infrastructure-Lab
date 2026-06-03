## Incident Summary

After restoring internet connectivity through USB tethering, remote administration of the Jumpertech infrastructure node remained unreliable under standard SSH-based access methods.

The mobile-tethered environment introduced dynamic addressing and NAT-related limitations that prevented consistent host reachability.

This impacted the ability to maintain stable remote administrative control of the infrastructure node.

![[Snapshot_2026-05-23_11-04-24.png]]



## Affected System

| Component | Description |
|---|---|
| Device | Jumpertech EZBook S5 |
| Connectivity Method | Oppo A3S USB tethering |
| Impact Area | Remote administration and system access |



## Initial Symptoms

Observed behavior included:

- inconsistent SSH reachability
- unreliable host accessibility across network changes
- dependency on dynamically assigned local IP addresses
- unstable remote administration workflow



## Diagnostic Actions Performed

The following troubleshooting actions were performed:

- evaluated SSH connectivity behavior under tethered network conditions
- observed DHCP-based address changes across sessions
- analyzed network accessibility limitations introduced by mobile tethering
- tested overlay networking solution using Tailscale



## Findings

Diagnostic results indicated:

- SSH service itself remained functional
- instability originated from network-layer addressing and NAT behavior
- mobile tethering environment could not provide reliable persistent host reachability
- overlay networking successfully bypassed local network dependency



## Root Cause Assessment

Dynamic addressing and NAT constraints introduced by mobile tethering prevented reliable direct host accessibility.

Contributing factors included:

- DHCP-assigned address changes
- absence of stable local network infrastructure
- restricted inbound connectivity under tethered network environment



## Resolution / Workaround

Tailscale was deployed across both administrative and infrastructure systems.

This established:

- persistent device identity
- overlay-based private networking
- stable remote administrative connectivity independent of local network topology

SSH operations were transitioned to the Tailscale virtual network layer.



## Outcome

Reliable remote administration capability was successfully restored.

Results achieved:

- stable remote shell access
- persistent inter-device connectivity
- elimination of dependency on changing local network addresses
- improved infrastructure manageability under constrained network conditions



## Operational Impact

This incident directly influenced infrastructure architecture decisions including:

- adoption of overlay networking as core access layer
- reduced dependency on physical network consistency
- prioritization of identity-based connectivity over local addressing



## Lessons Learned

- SSH instability is often caused by underlying network topology rather than SSH itself
- Mobile tethering environments introduce operational networking constraints
- Overlay networking can stabilize infrastructure management under unstable network conditions
- Persistent device identity simplifies constrained infrastructure administration