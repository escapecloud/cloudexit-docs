# Assessment Types

cloudexit supports multiple **assessment types** as part of the cloud exit readiness assessment.

Assessment types help cloudexit determine what level of dept of analysis and reporting should be generated.

In configuration files, this is represented as `assessmentType`.

**Types**

| Type | Value | Description |
|------|------:|-------------|
| Basic | 1 | Works offline. No account or API key required. |
| Standard | 2 | Enables richer scoring and reporting (Connected mode required). |


**Basic assessment (offline)**

The **Basic** assessment is designed to work entirely offline.

It typically includes:
- resource inventory
- cost overview
- portability constraints and risk inventory
- baseline reporting

This mode is free to use forever and does not require an account.


**Standard assessment (advanced)**

The **Standard** assessment enables more advanced scoring and reporting.

Depending on your setup, it may:
- use enhanced scoring models
- generate richer reports
- allow integration with connected platforms (exitcloud.io / escapecloud.io)

If you are running a connected workflow, Standard assessments require an API key.
