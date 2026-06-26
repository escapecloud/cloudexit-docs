# Non-Interactive Mode

Non-interactive mode is designed for CI/CD pipelines and scripted execution where no terminal prompts are allowed.

Use:

```bash
python3 main.py <provider> --non-interactive
```

Supported providers:

- AWS: `python3 main.py aws --non-interactive`
- Azure: `python3 main.py azure --non-interactive`

**How it works**

When `--non-interactive` is enabled, cloudexit reads required inputs from environment variables. If a required value is missing, the run fails fast with a typed non-zero exit code instead of waiting for user input.

This makes runs deterministic and safe for:

- GitHub Actions
- Scheduled jobs
- Scripted batch assessments

**Authentication options**

Both providers support two authentication patterns in non-interactive mode:

- Static credentials (long-lived secrets)
- OIDC/federated credentials (short-lived tokens)

OIDC is recommended for production CI where possible.
