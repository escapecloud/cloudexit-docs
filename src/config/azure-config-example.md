# Microsoft Azure config

This page shows an example configuration file for running an Azure assessment.

![image](/docs/images/Azure_Config.png)


**Example Azure config**

```json
{
  "name": "DMS System",
  "cloudServiceProvider": 1,
  "exitStrategy": 3,
  "assessmentType": 1,
  "providerDetails": {
    "clientId": "a5d7a310-26a4-115f-b679-ca01f0d73b75",
    "clientSecret": "",
    "tenantId": "38986009-9ded-42b3-b187-55f1cb61560a",
    "subscriptionId": "1299bf9a-8ca8-478b-8659-c62e62cd7baa",
    "resourceGroupName": "test-project"
  }
}
```

**Run with the config**

Save your config (for example as `config/azure.json`) and run:

```bash
python3 main.py azure --config config/azure.json
```

**Notes**

- Keep your `clientId` and `clientSecret` secure.
- Do not commit real credentials to GitHub.
