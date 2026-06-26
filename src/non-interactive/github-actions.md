# GitHub Actions

This page shows the recommended non-interactive setup for GitHub Actions.

## AWS - Static Auth

```yaml
name: cloudexit-aws-static
on:
  workflow_dispatch:

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run cloudexit
        env:
          ESC_EXIT_STRATEGY: "1"
          ESC_ASSESSMENT_TYPE: "1"
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: ${{ vars.AWS_DEFAULT_REGION }}
        run: python3 main.py aws --non-interactive
```

## AWS - OIDC Auth

```yaml
name: cloudexit-aws-oidc
on:
  workflow_dispatch:

permissions:
  id-token: write
  contents: read

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Configure AWS credentials (OIDC)
        uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: ${{ secrets.AWS_ROLE_TO_ASSUME }}
          aws-region: ${{ vars.AWS_DEFAULT_REGION }}

      - name: Run cloudexit
        env:
          ESC_EXIT_STRATEGY: "1"
          ESC_ASSESSMENT_TYPE: "1"
          AWS_DEFAULT_REGION: ${{ vars.AWS_DEFAULT_REGION }}
        run: python3 main.py aws --non-interactive
```

## Azure - Static Auth

```yaml
name: cloudexit-azure-static
on:
  workflow_dispatch:

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run cloudexit
        env:
          ESC_EXIT_STRATEGY: "1"
          ESC_ASSESSMENT_TYPE: "1"
          ESC_SUBSCRIPTION_ID: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
          ESC_RESOURCE_GROUP: ${{ secrets.AZURE_RESOURCE_GROUP }}
          AZURE_TENANT_ID: ${{ secrets.AZURE_TENANT_ID }}
          AZURE_CLIENT_ID: ${{ secrets.AZURE_CLIENT_ID }}
          AZURE_CLIENT_SECRET: ${{ secrets.AZURE_CLIENT_SECRET }}
        run: python3 main.py azure --non-interactive
```

## Azure - OIDC Auth

```yaml
name: cloudexit-azure-oidc
on:
  workflow_dispatch:

permissions:
  id-token: write
  contents: read

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Azure login (OIDC)
        uses: azure/login@v2
        with:
          client-id: ${{ secrets.AZURE_CLIENT_ID_OIDC }}
          tenant-id: ${{ secrets.AZURE_TENANT_ID }}
          subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}

      - name: Run cloudexit
        env:
          ESC_EXIT_STRATEGY: "1"
          ESC_ASSESSMENT_TYPE: "1"
          ESC_SUBSCRIPTION_ID: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
          ESC_RESOURCE_GROUP: ${{ secrets.AZURE_RESOURCE_GROUP }}
          AZURE_TENANT_ID: ${{ secrets.AZURE_TENANT_ID }}
          AZURE_CLIENT_ID: ${{ secrets.AZURE_CLIENT_ID_OIDC }}
        run: python3 main.py azure --non-interactive
```

## Using the cloudexit GitHub Action wrapper

If you prefer the action wrapper instead of direct CLI invocation, see:

- [escapecloud/cloudexit-actions](https://github.com/marketplace/actions/github-action-for-cloudexit)

The action supports:

- `auth-mode: static`
- `auth-mode: oidc`
