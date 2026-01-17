# What gets uploaded

When running cloudexit in **Connected mode**, only a **minimal, structured summary** of the assessment is uploaded to the platform.

The goal is to:
- respect data minimization principles
- avoid uploading sensitive information
- enable richer online reports and scoring

cloudexit always performs the basic assessment **locally** first.

**Summary**

The uploaded payload contains:

- assessment metadata (timestamps, provider, exit strategy)
- aggregated **Resource Inventory**
- aggregated **Cost Overview**

No credentials, secrets, or raw configuration data are uploaded.

**Resource Inventory**

The Resource Inventory payload contains **aggregated counts**, not raw resource identifiers.

For each detected resource type, the payload includes:
- resource type identifier
- location/region (if available, otherwise `unknown`)
- number of resources

Example:

```json
{
  "id": 12,
  "location": "eu-central-1",
  "count": 36
}
```

**Cost Overview**

Cost data is uploaded as **monthly aggregates**.

Each entry includes:
- billing month
- total cost for the month
- currency

Example:

```json
{
  "month": "2024-12",
  "cost": 1234.56,
  "currency": "USD"
}
```


**IMPORTANT**

cloudexit does **not** upload:

- access keys, secrets, tokens, or client credentials
- resource names, ARNs, tags, or IDs
- raw billing line items
- local databases or report files
