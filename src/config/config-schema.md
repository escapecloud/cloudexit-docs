# Config schema

cloudexit supports running assessments using configuration files.

Configuration files are useful when you want to:
- run assessments repeatedly in a consistent way
- automate runs in CI or scripts
- store non-secret defaults (scope, provider, strategy)

### `name`
Assessment name shown in reports.

Example:
```json
"name": "DMS System"
```

### `cloudServiceProvider`
Which cloud provider to assess.

| Cloud Provider | Value |
|--------------|------:|
| Microsoft Azure | 1 |
| Amazon Web Services | 2 |
| Google Cloud Platform | TBD |
| Alibaba Cloud | TBD |

### `exitStrategy`
Which exit strategy the assessment should model.

| Strategy | Value |
|---------|------:|
| Repatriation to On-Premises | 1 |
| Hybrid Cloud Adoption | TBD |
| Migration to Alternate Cloud | 3 |

### `assessmentType`
Which assessment type to run.

| Type | Value | Comment |
|------|------:|---------|
| Basic | 1 | No API key required |
| Standard | 2 | API key required |

### `providerDetails`
Provider-specific authentication details (varies by cloud provider).

See:
- [AWS config example](aws-config-example.md)
- [Azure config example](azure-config-example.md)

## Example structure

```json
{
  "name": "DMS System",
  "cloudServiceProvider": 2,
  "exitStrategy": 3,
  "assessmentType": 1,
  "providerDetails": {
    "...": "..."
  }
}
```
