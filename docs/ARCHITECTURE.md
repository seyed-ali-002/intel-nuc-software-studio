# Architecture

## Layers

### GUI
PySide6/Qt 6 application. No direct hardware writes.

### IPC
D-Bus API. Requests are typed, validated and authorized.

### Daemon
`nucd` owns lifecycle, policies, state, safety and privileged operations.

### Core
Contains capability manager, profile manager, monitoring engine, policy engine, safety engine and event bus.

### Hardware abstraction
Stable interfaces:
- PlatformBackend
- FanBackend
- BatteryBackend
- LightingBackend
- KeyboardBackend
- GpuBackend
- MonitoringBackend

### Backends
Implement Linux-native and hardware-specific adapters.

## Suggested repository layout

```text
nuc-control/
├── apps/
│   ├── daemon/
│   ├── gui/
│   └── cli/
├── src/
│   ├── core/
│   ├── hardware/
│   ├── ipc/
│   ├── monitoring/
│   ├── profiles/
│   ├── safety/
│   └── diagnostics/
├── configs/
├── packaging/
├── systemd/
├── tests/
├── docs/
└── scripts/
```

The exact layout may be refined after Phase 0.
