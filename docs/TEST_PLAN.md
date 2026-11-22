# Test Plan

## Unit
- capability state transitions
- profile validation
- fan curve validation
- range checks
- configuration serialization
- policy evaluation
- error handling

## Integration
- daemon starts/stops
- D-Bus authorization
- sysfs/hwmon reads
- power_supply reads/writes where supported
- LED operations
- NVIDIA integration
- profile persistence

## Hardware
- cold boot
- warm reboot
- shutdown
- suspend/resume
- AC connect/disconnect
- battery operation
- CPU load
- GPU load
- combined load
- fan automatic mode
- validated manual fan control
- RGB
- lightbar
- charge limit

## Safety
- invalid fan values
- invalid charge limit
- unsupported feature
- daemon crash
- GUI crash
- backend timeout
- sensor disappearance
- thermal emergency
- partial hardware failure

## Compatibility
Test representative releases of Debian/Ubuntu, Fedora, Arch-based and openSUSE where feasible. Record exact distro and kernel versions.

## Release gate
No release may expose an unsafe hardware-control feature as enabled merely because a write operation did not immediately error.
