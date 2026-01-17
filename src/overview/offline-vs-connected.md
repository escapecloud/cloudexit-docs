# Offline vs Connected mode

cloudexit supports two workflows:

**Offline mode (default)**

Offline mode is the standard cloudexit workflow:

- runs locally on your machine
- connects to your cloud provider using the credentials you provide
- generates reports locally
- stores all results locally under the `reports/` directory

Ideal when:
- you want full control over assessment data
- you cannot upload metadata outside your environment
- you want a free and lightweight workflow

**Connected mode (optional)**

Connected mode allows you to connect cloudexit to:

- **exitcloud.io** - Lightweight Cloud Exit Readiness Platform for MSPs and SMEs
- **escapecloud.io** - Cloud Exit Readiness Platform for Enterprises

With connected mode, cloudexit can upload assessment outputs so you can:

- store assessments centrally
- generate richer reports with additional scoring
- compare results across multiple assessments over time
- share and export reports more easily

Ideal when:
- you want assessment history and comparisons
- you run assessments for multiple environments or customers
- you want deeper reporting and scoring models
