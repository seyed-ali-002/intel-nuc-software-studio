# Compatibility Strategy

## Distribution support

Primary targets:
- Ubuntu/Debian
- Fedora
- Arch/Manjaro
- openSUSE

The application must detect package manager, desktop session, init system and relevant runtime services.

## Kernel support

Do not use a hard-coded kernel-version allowlist as the primary mechanism.

Instead:
1. Detect the interface.
2. Validate semantics.
3. Run a non-destructive probe.
4. Mark capability state.
5. Use a backend/fallback if available.

## Desktop support

The GUI should work on common Qt-compatible Linux desktop environments. OSD and desktop-specific behavior must have adapters.

## Unsupported systems

The application must still start in read-only/diagnostic mode when hardware control is unavailable.
