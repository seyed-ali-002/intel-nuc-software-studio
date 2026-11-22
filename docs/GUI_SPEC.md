# GUI Specification

## Design goal
A clean control center with the simplicity and visual hierarchy of Intel NUC Software Studio, adapted to Linux.

## Main navigation
- Dashboard
- Performance
- Cooling
- Lighting
- Battery
- Monitoring
- Profiles
- Diagnostics
- Settings

## Dashboard
Show:
- active profile
- CPU/GPU temperatures
- CPU/GPU load
- fan RPM
- RAM
- battery
- quick profile switch

## Performance
Large profile selector plus advanced controls hidden behind an Advanced section.

## Cooling
Live fan RPM and graphical fan curve editor.

## Lighting
Keyboard RGB and Lightbar as separate cards.

## Battery
Charge state and charge limit.

## Diagnostics
Compatibility matrix, backend status, warnings and export.

## UX rules
- Do not expose raw sysfs paths on normal screens.
- Use clear unavailable/partial states.
- Dangerous controls require confirmation.
- Show the effective state after every change.
- Avoid excessive animation.
- Support keyboard navigation and accessibility.
