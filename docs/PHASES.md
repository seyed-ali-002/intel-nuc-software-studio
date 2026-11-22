# Implementation Phases

## Phase 0 — Research and specification
Deliver:
- complete feature matrix against Intel NUC Software Studio
- hardware target specification
- Linux interface inventory plan
- dependency and licensing review
- risk register
- architecture decision record

Exit criteria:
- no unknown critical hardware-control assumption remains untracked.

## Phase 1 — Hardware discovery
Collect DMI, PCI, USB, kernel, module, hwmon, power_supply, LED and NVIDIA information.

Deliver:
- `hardware-report.json`
- capability matrix
- raw evidence archive
- compatibility notes

## Phase 2 — Kernel / ACPI / EC validation
Validate native `uniwill-laptop` interfaces and other safe Linux interfaces.

Deliver:
- validated interface map
- known kernel limitations
- no unverified EC writes.

## Phase 3 — Hardware abstraction layer
Implement interfaces for detection, monitoring, battery, fan, lighting, NVIDIA and platform controls.

Deliver:
- backend contracts
- capability engine
- mock backends for development.

## Phase 4 — Monitoring
Implement sampling, event handling, metrics model and dashboard data.

Deliver:
- stable metrics API
- resource-efficient monitoring.

## Phase 5 — Power/performance
Implement validated CPU/GPU policy controls and profiles.

Deliver:
- Quiet/Balanced/Performance/Custom
- safe fallback.

## Phase 6 — Fan engine
Implement automatic mode, validated manual control, curve editor model, hysteresis and thermal emergency policy.

## Phase 7 — RGB/lightbar
Implement controller abstraction, keyboard RGB and lightbar with capability-aware UI.

## Phase 8 — Battery and hardware controls
Implement charge limit and supported hardware toggles.

## Phase 9 — Profiles and automation
Implement persistent profiles, import/export and optional automatic profile switching.

## Phase 10 — Daemon and IPC
Implement privileged daemon, D-Bus API, authorization and lifecycle management.

## Phase 11 — CLI
Implement `nucctl` for status, profiles, diagnostics and supported controls.

## Phase 12 — GUI
Implement Dashboard, Performance, Fan, RGB, Battery, Monitoring, Profiles, Diagnostics and Settings.

## Phase 13 — OSD/hotkeys
Implement event notifications, OSD and supported hotkeys.

## Phase 14 — Testing
Unit, integration, hardware, thermal, sleep/wake, reboot, shutdown, AC/battery and failure testing.

## Phase 15 — Packaging
DEB/RPM/Arch/Flatpak/AppImage as technically appropriate. Native packages are prioritized for hardware integration.

## Phase 16 — Documentation and release
User, developer and hardware documentation; compatibility matrix; changelog; release checklist.

## Phase execution rule
Do not start a later phase by guessing results from an earlier phase. Each phase consumes the verified artifacts produced by the previous phase.
