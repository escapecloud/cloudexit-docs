# Non-Interactive AWS

Use non-interactive AWS mode when you want cloudexit to run without prompts.

```bash
python3 main.py aws --non-interactive
```

**Required inputs**

Always required:

- `ESC_EXIT_STRATEGY`
- `ESC_ASSESSMENT_TYPE`
- `AWS_DEFAULT_REGION` (or `AWS_REGION`)

**Static credentials**

Also set:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`

**OIDC credentials**

Also set:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_SESSION_TOKEN`

In GitHub Actions, these are typically injected by `aws-actions/configure-aws-credentials`.
