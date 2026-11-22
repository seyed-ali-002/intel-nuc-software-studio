# Project Specification

## 1. Scope

NUC Control Center is a Linux desktop control center intended to provide a clean, unified interface for hardware monitoring and supported hardware controls on Intel NUC X15 / compatible Uniwill systems.

The initial hardware target is LAPKC71F. The architecture must not hard-code the GUI to that model.

## 2. Product principles
1. Linux-native where possible.
2. Capability-driven rather than distro-driven.
3. Hardware access isolated behind backends.
4. Safety before convenience.
5. GUI never requires root.
6. Graceful degradation when a feature is unavailable.
7. Observable behavior through logs and diagnostics.
8. No destructive EC operations without validated hardware-specific implementation.

## 3. Functional requirements

### Monitoring
- CPU usage, temperature, frequency and power where available.
- GPU usage, temperature, frequency, VRAM and power where available.
- RAM and swap.
- Storage usage, temperature and I/O where available.
- Network RX/TX.
- Battery percentage, charging state, power and health where available.
- Fan RPM for every detected fan.

### Performance and power
- Quiet, Balanced, Performance and Custom profiles.
- Optional Gaming/Turbo profile when hardware supports it.
- CPU policy integration.
- GPU power/TGP integration only where a validated backend exists.
- Automatic profile switching must be opt-in.
- Every setting must be validated before applying.

### Cooling
- Automatic fan mode.
- Manual fan control only on validated hardware.
- Graphical fan curve editor.
- Per-fan curves where supported.
- Hysteresis and emergency thermal policy.
- Safe fallback if the daemon stops.

### Keyboard and lighting
- Keyboard RGB.
- Per-key RGB where the controller supports it.
- Effects, color, brightness and speed.
- Lightbar control where supported.
- Separate keyboard and lightbar backends.

### Battery
- Battery monitoring.
- Charge limit where supported.
- Validation and safe ranges.
- Persistence only when the underlying interface supports safe persistence.

### Controls
- Fn lock where supported.
- Super/Windows key where supported.
- Touchpad toggle where supported.
- NumLock and other exposed controls where supported.
- Hotkeys and OSD.

### Profiles
Profiles contain power, cooling, RGB, lightbar and other supported policies.
Profiles are stored in a versioned format and can be exported/imported.

### Diagnostics
The application must report:
- OS/distribution
- kernel
- model/DMI
- CPU/GPU
- driver/backend status
- available capabilities
- failed checks
- warnings
- relevant logs

A diagnostic report must be exportable.

## 4. Non-functional requirements

### Compatibility
The project targets common Linux distributions including Debian/Ubuntu, Fedora, Arch-based distributions and openSUSE. No feature may depend on a single package manager.

Kernel compatibility must be capability-based. Avoid version checks unless a real compatibility break requires them.

### Security
- GUI runs as a normal user.
- Privileged daemon performs restricted hardware operations.
- D-Bus is the preferred IPC mechanism.
- polkit or equivalent authorization controls privileged actions.
- No blanket chmod/chown workarounds.
- No arbitrary EC register access exposed to users.

### Reliability
- Daemon watchdog.
- Safe fallback.
- State validation.
- Structured logging.
- Recovery after GUI restart.
- Clean shutdown handling.

### UX
The UI should closely resemble the clarity and simplicity of the original Software Studio while using Linux-native patterns. Technical details belong in Diagnostics/Advanced pages rather than the main dashboard.

## 5. Capability model

Every feature has one of:
- supported
- partial
- unavailable
- unsupported
- blocked_by_permission
- blocked_by_kernel
- blocked_by_backend
- unsafe

The GUI must render these states without crashing.

## 6. Architecture

GUI -> D-Bus -> privileged daemon -> Core/Policy -> Hardware Abstraction -> backend -> Linux interface/hardware.

Backends may use:
- sysfs
- hwmon
- power_supply
- LED subsystem
- ACPI
- validated Uniwill interfaces
- NVIDIA interfaces
- validated controller-specific tools/libraries

Third-party projects may be used as references or optional backends, but the core architecture must not become dependent on one project.

## 7. Technology direction

Recommended:
- Python 3 for daemon/CLI during the initial implementation.
- PySide6/Qt 6 for the desktop GUI.
- D-Bus for IPC.
- systemd service on systemd systems.
- native package integration per distribution.
- YAML or TOML for human-editable profiles; JSON for machine-generated diagnostic/report data.

Technology choices remain subject to Phase 0/1 validation.

## 8. Safety model

All hardware writes pass through:
validate -> range check -> capability check -> thermal/power safety check -> apply -> verify -> log.

A failed write must never silently appear successful.

## 9. Definition of Done

A feature is done only if:
- implementation exists,
- capability detection exists,
- unsupported case is handled,
- logging exists,
- unit tests exist where applicable,
- integration/hardware test exists where applicable,
- GUI state is correct,
- documentation exists,
- recovery behavior is defined,
- packaging does not break it.
