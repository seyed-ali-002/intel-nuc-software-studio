# Profile Format

Profiles are versioned.

Example:

```yaml
version: 1
name: Balanced
power:
  cpu_policy: balanced
  gpu_policy: balanced
cooling:
  mode: auto
lighting:
  keyboard:
    enabled: true
    effect: static
    brightness: 60
  lightbar:
    enabled: true
battery:
  charge_limit: 80
automation:
  enabled: false
```

Unsupported fields must not be silently applied. The profile loader should report them and preserve forward compatibility where possible.
