# Security Model

## Threats
- unauthorized privileged hardware writes
- malformed D-Bus requests
- accidental unsafe fan/power values
- malicious local process attempting control
- stale state after daemon crash

## Controls
- normal-user GUI
- least-privilege daemon
- polkit/D-Bus authorization
- strict input validation
- allowlisted operations
- bounded numeric values
- audit logging
- safe defaults
- timeout handling

## EC policy
Raw arbitrary EC read/write is not a public API. Any EC-specific backend must be hardware-specific, reviewed and protected by capability checks.

## Reporting
Security issues should be documented with reproduction steps, affected hardware/kernel, logs and mitigation.
