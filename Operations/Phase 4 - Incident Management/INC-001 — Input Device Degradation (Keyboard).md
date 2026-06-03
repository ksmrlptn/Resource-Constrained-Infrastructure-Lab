## Incident Summary

The primary compute node exhibits partial keyboard failure and instability affecting core input functionality. This impacts direct system interaction and reinforces dependency on remote administration via external control machine.



## Affected Components

- Keyboard (built-in input device)
- Specific keys:
  - `W` key: non-functional
  - `2` key: non-functional
  - `S` key: unstable (intermittent response)



## Impact

### Operational Impact
- Direct local administration is significantly degraded
- Text input reliability is reduced
- Basic system navigation becomes inconsistent

### Workflow Impact
- System administration must be performed remotely
- Increased dependency on Lenovo ThinkPad (administrative machine)
- Encourages use of SSH over Tailscale for stable input/output handling



## Observed Behavior

- Certain keys produce no input response
- Some keys respond intermittently depending on pressure or timing
- Input inconsistency increases under prolonged usage



## Root Cause

Likely hardware aging or physical keyboard degradation due to:
- wear over time
- mechanical failure of key switches or membrane
- general device aging

No software-level fault identified.



## Workaround / Mitigation

- Primary administration shifted to remote access via Tailscale
- All system control performed through Lenovo ThinkPad
- Direct interaction with Jumpertech minimized



## Outcome

This limitation reinforces the design decision to operate the Jumpertech system as a headless infrastructure node, controlled remotely rather than used directly as a workstation.