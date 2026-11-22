# NUC Control Center

A Linux-native control center for Intel NUC X15 / Uniwill hardware, initially targeting LAPKC71F, with a UI inspired by Intel NUC Software Studio.

## Project goals
- Reproduce the useful functionality of Intel NUC Software Studio on Linux.
- Add Linux-native monitoring, diagnostics, safety, profiles, CLI, D-Bus IPC, logging and recovery.
- Support multiple Linux distributions and kernel versions through capability detection and backend abstraction.
- Never assume that a feature exists merely because a sysfs path or third-party tool exists.
- Keep privileged hardware operations inside a daemon; never run the GUI as root.

## Initial target
- Intel NUC X15 LAPKC71F
- Intel Core i7-11800H
- NVIDIA RTX 3070
- Linux-first architecture

## Definition of Done
A release is complete only when implemented features have passed unit, integration, hardware, safety, packaging and GUI validation, with documented limitations.

See `docs/PROJECT_SPEC.md` for the full specification and `docs/PHASES.md` for the implementation plan.
