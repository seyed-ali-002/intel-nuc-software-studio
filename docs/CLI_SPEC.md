# CLI Specification

Command name: `nucctl`

Examples:

```bash
nucctl status
nucctl capabilities
nucctl profile list
nucctl profile set performance
nucctl fan status
nucctl fan curve show
nucctl battery status
nucctl battery limit 80
nucctl rgb status
nucctl lightbar status
nucctl diagnostics run
nucctl diagnostics export report.json
```

Commands must return meaningful exit codes and structured output options.

No CLI command may bypass daemon safety checks.
