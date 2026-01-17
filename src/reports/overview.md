# Reports Overview

cloudexit generates reports automatically at the end of each assessment.

Reports are designed to help you answer:

- What cloud services are currently in use (Resource Inventory)?
- How costs evolved over time (Cost Overview)?
- Where portability constraints and vendor lock-in risks exist (Risk Inventory)?
- What alternative technologies can replace the services in use (Alternative Technologies)?
- How prepared you are for an exit scenario (Scoring)? (only in Connected mode)

![image](/docs/images/Report-Screen.png)

## Structure

A typical report contains:

- Resource Inventory
- Cost Overview
- Risk Inventory
- Alternative Technologies
- Scores *(only in Connected mode)*

## Location

Each assessment creates a timestamped folder under:

```text
reports/<timestamp>/
```

Open the HTML or PDF report:

```text
reports/<timestamp>/index.html
reports/<timestamp>/report.pdf
```

## Formats

**Basic (offline)**

- Resource Inventory
- Cost Inventory
- Risk Inventory
- Alternative Technologies
- Executive Summary (HTML / PDF)

**Standard (only in Connected mode)**

- Resource Inventory
- Cost Inventory
- Risk Inventory
- Alternative Technologies
- Scoring
- Executive Summary (on exitcloud.io or escapecloud.io)
- Exit Readiness Report (on exitcloud.io or escapecloud.io)
