# Offline vs. Online reports

cloudexit supports two reporting modes:

- **Offline**
- **Online (Connected)**

Both start from the same local assessment engine.

## Offline

Offline mode focuses on a lightweight, self-contained workflow.

You get:
- a local HTML report under `reports/<timestamp>/index.html`
- sections covering:
  - Resource Inventory
  - Cost Overview
  - Risk Inventory
  - Alternative Technologies

Offline reports:
- require no account
- require limited internet connection
- do not include scoring
- are generated once per run

This mode is ideal for:
- exploratory assessments
- one-time reviews
- restricted environments

## Online

Connected mode extends the same local run with a platform workflow.

You get:
- richer PDF reports hosted on the platform:
  - Executive Summary
  - Exit Readiness Report (from 'Standard' assessment)
- scoring and benchmarking *(only in Connected mode)*

## Key differences

| Area | Offline (Basic) | Online (Connected) |
|-----|------------------|--------------------|
| Internet required | Yes | Yes |
| Account required | No | Yes |
| Data storage | Local | Local & Platform |
| HTML report | Local | Local & Platform |
| PDF reports | Limited | Executive + Exit Readiness (if Standard) |
| Scoring | No | Yes (if Standard) |
| Continuous assessments | No | Yes (platform-initiated) |
