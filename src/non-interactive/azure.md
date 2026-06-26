# Non-Interactive Azure

Use non-interactive Azure mode when you want cloudexit to run without prompts.

```bash
python3 main.py azure --non-interactive
```

**Required inputs**

Always required:

- `ESC_EXIT_STRATEGY`
- `ESC_ASSESSMENT_TYPE`
- `ESC_SUBSCRIPTION_ID`
- `ESC_RESOURCE_GROUP`
- `AZURE_TENANT_ID`

**Static credentials**

Also set:

- `AZURE_CLIENT_ID`
- `AZURE_CLIENT_SECRET`

**OIDC credentials**

Also set:

- `AZURE_CLIENT_ID`

In OIDC mode, `AZURE_CLIENT_SECRET` is intentionally omitted and cloudexit uses `DefaultAzureCredential` with federated identity from the runtime environment.

In GitHub Actions, run `azure/login` before cloudexit to initialize OIDC context.
