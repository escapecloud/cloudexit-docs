# Data Landscape & Egress Estimation

This feature adds an optional egress estimation step to a completed assessment.

**Use feature**

Add `--egress` to any assessment to measure how much data lives in the assessed scope and estimate the one-time internet egress fee for moving it out — based on the provider's tiered list prices, with no additional permissions required.

```bash
python3 main.py azure --cli --egress
python3 main.py aws --profile PROFILE --egress
```

**How it works**

When enabled, cloudexit runs **Stage #7 - Egress Estimation** after the main report has already been generated.

If Stage 7 fails:

- the finished assessment report is still kept
- the CLI exits with code `9` (`EGRESS`)
- all other stages and exit codes stay unchanged

**Outputs**

- **`egress.html`**: Interactive dashboard with the estimated egress fee, data allocation, and data landscape.
- **`egress.pdf`**: Executive summary of the egress estimate, data landscape, and pricing appendix.
- **`egress_estimate.json`**: Machine-readable egress sizing and estimation data for the assessment.
