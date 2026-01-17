# Authentication & Permissions

Most cloudexit issues are related to authentication or permissions.

**Cloud provider authentication**

cloudexit supports multiple authentication methods depending on the provider:

- CLI-based authentication (e.g. AWS profile, Azure CLI)
- Configuration file credentials
- Interactive (in terminal)

Ensure the authentication method you use is supported by the selected cloud provider.

**Required permissions**

cloudexit requires **read-only** permissions to perform an assessment.

Examples:
- AWS: `ViewOnlyAccess`, `AWSBillingReadOnlyAccess`
- Azure: `Reader`, `Cost Management Reader`

Missing permissions may result in:
- incomplete inventories
- missing cost data
- failed assessments

**Platform authentication (Connected mode)**

Connected mode requires:
- a valid API key
- sufficient credits
- correct platform host configuration

Verify these settings in `config.py` before running a connected assessment.

**Best practices**

- Use dedicated read-only roles or service principals
- Avoid using personal admin credentials
- Rotate keys regularly
