## Objective

Stabilize remote monitoring and access for Jumpertech using a consistent, persistent, and simple architecture based on Tailscale and systemd-managed service.

![[Snapshot_2026-06-03_20-03-18.png]]



## Current State

- Jumpertech runs Linux (Arch-based environment)
- Glances is deployed as a systemd service
- Remote access is performed via Tailscale network
- SSH is available for administration
- Monitoring access has been inconsistent due to multiple access methods (localhost, SSH tunnels, direct IP binding)



## Improvement Goal

Establish a single, stable, and predictable monitoring access model that:

- survives reboot
- does not depend on SSH tunnels
- does not require changing service bindings
- works consistently across ThinkPad and Oppo A3S via Tailscale



## Implementation

### 1. Standardize Monitoring Service

- Run Glances as a persistent systemd service
- Keep binding simple and consistent

```
ExecStart=/home/khas/glances-env/bin/glances -w
```



### 2. Standardize Network Access

Use only Tailscale-based access paths:

- Primary access:

  ```
   http://100.69.198.45:61208
  ```

Do not use:

- SSH port forwarding
- localhost tunneling
- dynamic bind switching



### 3. Remove Access Fragmentation

Eliminate:

- 127.0.0.1-only mode for remote services
- mixed binding strategies
- multiple concurrent access methods for the same service



### 4. System Behavior Requirements

- Service must auto-restart on failure
- Service must start on boot
- Service must remain accessible without manual intervention
- Network exposure controlled by Tailscale, not service binding changes



## Resulting Architecture

```
ThinkPad / Oppo A3S
   ↓
Tailscale Network
   ↓
Jumpertech
   ↓
Glances Service (systemd)
```



## Outcome

- Single access method for monitoring
- Reduced configuration complexity
- Stable remote observability
- Improved reliability under reboot and network changes