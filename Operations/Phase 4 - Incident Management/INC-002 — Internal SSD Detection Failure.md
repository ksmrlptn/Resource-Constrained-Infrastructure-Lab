## Incident Summary

The Jumpertech EZBook S5 failed to consistently detect the installed internal M.2 SATA SSD during system boot and initialization.

This prevented reliable operating system installation and stable system operation using the laptop’s internal storage interface.

The incident impacted the ability to deploy the infrastructure node using conventional internal storage configuration.

![[IMG_20260512_160506_356.jpeg|278]]



## Affected System

| Component | Description |
|---|---|
| Device | Jumpertech EZBook S5 |
| Storage Device | DTGC-C M.2 2280 SATA 128GB |
| Impact Area | System boot and storage detection |



## Initial Symptoms

Observed behavior included:

- Internal SSD intermittently missing from BIOS detection
- System failing to locate bootable storage device
- Inconsistent SSD visibility across multiple boot attempts
- OS installation reliability could not be guaranteed



## Diagnostic Actions Performed

The following troubleshooting actions were performed:

- Verified SSD detection behavior across repeated boots
- Tested SSD functionality outside internal connection path
- Connected SSD using external USB enclosure
- Confirmed SSD remained readable and operational externally
- Compared behavior between internal and external SSD access methods



## Findings

Diagnostic results indicated:

- SSD hardware remained functional when externally connected
- Failure behavior occurred only through internal storage interface
- Internal storage path could not provide stable communication with SSD

The issue was therefore isolated away from the SSD itself and toward the laptop’s internal storage interface or related hardware pathway.



## Root Cause Assessment

Hardware-level instability affecting the internal SSD connection path.

Possible contributing factors include:
- degraded internal connector/interface
- motherboard-level storage communication instability
- aging hardware-related detection failure



## Resolution / Workaround

Instead of replacing the system hardware, the infrastructure design was adapted to use:

- USB-to-M.2 SATA enclosure
- external SSD-based system deployment

The external storage path provided stable SSD detection and operational reliability.



## Outcome

The Jumpertech system was successfully repurposed as a functional infrastructure node despite internal hardware limitations.

Results achieved:

- successful Arch Linux deployment
- stable system boot operation
- continued infrastructure usability
- preservation of existing hardware under constrained budget conditions



## Operational Impact

This incident directly influenced infrastructure design decisions, including:

- adoption of externalized storage dependency
- emphasis on recovery-oriented infrastructure planning
- acceptance of hardware constraints as part of operational architecture



## Lessons Learned

- Hardware failure does not always require hardware replacement
- Functional isolation testing is critical during troubleshooting
- Externalized components can extend operational lifespan of aging systems
- Constraint-driven adaptation can restore infrastructure usability without additional hardware investment