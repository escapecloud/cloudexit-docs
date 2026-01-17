# Common errors

This page lists common issues you may encounter when running cloudexit and how to resolve them.

**Assessment fails immediately**

**Possible causes:**
- Missing or invalid credentials
- Insufficient permissions

**What to check:**
- Verify credentials are correct and active
- Confirm required permissions are assigned
- Review CLI output for provider-specific error messages

**No resources detected**

**Possible causes:**
- Incorrect account, subscription, or project scope
- Region filtering excludes active resources

**What to check:**
- Ensure the correct account or subscription is used
- Review region or scope settings in the CLI or config file

**Cost data missing or incomplete**

**Possible causes:**
- Billing permissions not granted
- Cost data not yet available for recent periods

**What to check:**
- Verify required billing permissions
- Confirm the billing period contains usage data

**Upload to platform failed (Connected mode)**

**Possible causes:**
- Invalid API key
- No available credits
- Incorrect platform host
- Network connectivity issues

**What to check:**
- Verify `HOST` and `KEY` values in `config.py`
- Confirm credits are available on the platform
- Check outbound HTTPS connectivity

**Unexpected errors**

If you encounter an error not covered here:
- re-run the assessment with debug logging enabled
- capture the full CLI output
- open an issue in the GitHub repository with details
