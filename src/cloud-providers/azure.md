# Azure

This page explains how to authenticate CloudExit against Microsoft Azure and what permissions are required.

**Authentication Methods**

cloudexit supports:
- **Service principal** (interactive or config file)
- **Azure CLI credentials** (`--cli`)

**Required Permissions**

To run an Azure assessment, the following role assignments must be attached:

- **Reader** [(Microsoft Docs)](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/general#reader)
- **Cost Management Reader** [(Microsoft Docs)](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/management-and-governance#cost-management-reader)

These roles should be assigned at the appropriate scope:
- Subscription (recommended)
- Resource group (supported if you want a narrower scope)

See also: [Required permissions](required-permissions.md)

**Run an assessment (Azure)**

***Interactive***

```bash
python3 main.py azure
```

cloudexit will prompt you for:
- Exit strategy
- Assessment type
- Tenant ID
- Service Principal / Client ID
- Client Secret ID

Then you've to select from the followings:
- Select Subscription Name / ID
- Select Resource Group Name

***Interactive with Azure CLI***

```bash
python3 main.py azure --cli
```

cloudexit will use your authenticated Azure CLI session.
[(Microsoft Docs)](https://learn.microsoft.com/en-us/cli/azure/)
