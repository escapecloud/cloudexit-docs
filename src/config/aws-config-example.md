# Amazon Web Services (AWS) config

This page shows an example configuration file for running an AWS assessment.

![image](/docs/images/AWS_Config.png)

**Example AWS config**

```json
{
  "name": "DMS System",
  "cloudServiceProvider": 2,
  "exitStrategy": 3,
  "assessmentType": 1,
  "providerDetails": {
    "accessKey": "AKAAXASJHMTOST9YTLHE",
    "secretKey": "",
    "region": "eu-central-1"
  }
}
```

**Run with the config**

Save your config (for example as `config/aws.json`) and run:

```bash
python3 main.py aws --config config/aws.json
```

**Notes**

- Keep your `accessKey` and `secretKey` secure.
- Do not commit real credentials to GitHub.
