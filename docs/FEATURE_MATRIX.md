# Feature Matrix

Status values: planned, discovered, validated, implemented, blocked, unavailable.

| Feature | Initial target | Linux source | Safety critical | Status |
|---|---|---|---|---|
| CPU temperature | LAPKC71F | hwmon | no | planned |
| GPU temperature | LAPKC71F | NVIDIA/hwmon | no | planned |
| Fan RPM | LAPKC71F | hwmon/Uniwill | medium | planned |
| Fan curve | LAPKC71F | validated backend | high | planned |
| Battery charge limit | LAPKC71F | power_supply/Uniwill | high | planned |
| Lightbar | LAPKC71F | LED/Uniwill | low | planned |
| Keyboard RGB | LAPKC71F | controller/backend | medium | planned |
| Per-key RGB | compatible controller | controller backend | medium | planned |
| Performance mode | LAPKC71F | platform/power backend | high | planned |
| GPU TGP | compatible NVIDIA hardware | NVIDIA/platform backend | high | planned |
| OSD | Linux desktop | Qt/desktop APIs | low | planned |
| Hotkeys | hardware/desktop | input APIs | medium | planned |
| Diagnostics | all | internal | no | planned |
| Profiles | all | internal | no | planned |
| Multi-distro | all | packaging/backend | no | planned |

This matrix must be updated with evidence after hardware discovery.
