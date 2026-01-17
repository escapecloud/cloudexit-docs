# Running assessments

cloudexit can run assessments:
- interactively via the CLI (recommended for first-time users)
- via configuration files (recommended for repeatable workflows)

This guide walks you through both.

## Interactive mode

### Amazon Web Services (AWS)

```bash
python3 main.py aws
python3 main.py aws --profile PROFILE
```

![image](/docs/images/AWS_Profile.png)

### Microsoft Azure

```bash
python3 main.py azure
python3 main.py azure --cli
```

![image](/docs/images/Azure_CLI.png)

cloudexit will guide you through:
- providing authentication details
- defining an optional assessment name (with the `--name` argument)
- selecting scope (based on the cloud provider)

When the assessment completes, cloudexit generates a report folder under `reports/`.

## Configuration file mode

### Amazon Web Services (AWS)

```bash
python3 main.py aws --config config.json
```

### Microsoft Azure

```bash
python3 main.py azure --config config.json
```

Configuration files are useful if you want to:
- run assessments repeatedly in a consistent way
- automate runs in CI or scripts
- share non-secret configuration defaults across your team

See:
- [Required permissions](../cloud-providers/required-permissions.md)
- [AWS](../cloud-providers/aws.md)
- [Azure](../cloud-providers/azure.md)
- [Config schema](../config/config-schema.md)
- [AWS config example](../config/aws-config-example.md)
- [Azure config example](../config/azure-config-example.md)

## Reports

Each assessment creates a new timestamped folder under `reports/`.

Typical contents include:
- raw output data
- standardized data
- generated HTML report
- generated PDF report

To view the report, open:

```
reports/<timestamp>/index.html
```
