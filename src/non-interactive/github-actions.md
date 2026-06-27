# GitHub Actions

This page shows the recommended non-interactive setup for GitHub Actions using the `cloudexit` action wrapper.

## AWS - Static Auth

```yaml
name: cloudexit-aws-static
on:
  workflow_dispatch:

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - name: Run cloudexit
        id: run_cloudexit
        uses: escapecloud/cloudexit-actions@v1
        with:
          provider: aws
          auth-mode: static
          exit-strategy: "1"
          assessment-type: "1"
          host: ""
          key: ""
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: ${{ vars.AWS_DEFAULT_REGION }}
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
      - name: Configure AWS credentials (OIDC)
        uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: ${{ secrets.AWS_ROLE_TO_ASSUME }}
          aws-region: ${{ vars.AWS_DEFAULT_REGION }}

      - name: Run cloudexit
        id: run_cloudexit
        uses: escapecloud/cloudexit-actions@v1
        with:
          provider: aws
          auth-mode: oidc
          exit-strategy: "1"
          assessment-type: "1"
          host: ""
          key: ""
        env:
          AWS_DEFAULT_REGION: ${{ vars.AWS_DEFAULT_REGION }}
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
      - name: Run cloudexit
        id: run_cloudexit
        uses: escapecloud/cloudexit-actions@v1
        with:
          provider: azure
          auth-mode: static
          exit-strategy: "1"
          assessment-type: "1"
          host: ""
          key: ""
        env:
          ESC_SUBSCRIPTION_ID: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
          ESC_RESOURCE_GROUP: ${{ secrets.AZURE_RESOURCE_GROUP }}
          AZURE_TENANT_ID: ${{ secrets.AZURE_TENANT_ID }}
          AZURE_CLIENT_ID: ${{ secrets.AZURE_CLIENT_ID }}
          AZURE_CLIENT_SECRET: ${{ secrets.AZURE_CLIENT_SECRET }}
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
      - name: Azure login (OIDC)
        uses: azure/login@v2
        with:
          client-id: ${{ secrets.AZURE_CLIENT_ID_OIDC }}
          tenant-id: ${{ secrets.AZURE_TENANT_ID }}
          subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}

      - name: Create federated token file for Docker action
        shell: bash
        run: |
          OIDC_TOKEN="$(curl -sS \
            -H "Authorization: bearer ${ACTIONS_ID_TOKEN_REQUEST_TOKEN}" \
            "${ACTIONS_ID_TOKEN_REQUEST_URL}&audience=api://AzureADTokenExchange" \
            | jq -r '.value')"

          TOKEN_FILE="${RUNNER_TEMP}/azure_federated_token"
          printf '%s' "${OIDC_TOKEN}" > "${TOKEN_FILE}"

          echo "AZURE_FEDERATED_TOKEN_FILE=${TOKEN_FILE}" >> "${GITHUB_ENV}"

      - name: Run cloudexit
        id: run_cloudexit
        uses: escapecloud/cloudexit-actions@v1
        with:
          provider: azure
          auth-mode: oidc
          exit-strategy: "1"
          assessment-type: "1"
          host: ""
          key: ""
        env:
          ESC_SUBSCRIPTION_ID: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
          ESC_RESOURCE_GROUP: ${{ secrets.AZURE_RESOURCE_GROUP }}
          AZURE_TENANT_ID: ${{ secrets.AZURE_TENANT_ID }}
          AZURE_CLIENT_ID: ${{ secrets.AZURE_CLIENT_ID_OIDC }}
          AZURE_FEDERATED_TOKEN_FILE: ${{ env.AZURE_FEDERATED_TOKEN_FILE }}
```
