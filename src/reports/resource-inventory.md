# Resource Inventory

The Resource Inventory summarizes the cloud services identified within the assessment scope.

It answers:

> What services are currently in use and how broad is the footprint?

## Why it matters

The size and diversity of your inventory often correlates with exit complexity:

- more services usually means more dependencies and migration work
- a larger footprint increases testing, refactoring, and operational change effort
- cloud service provider–specific services might have limited alternatives

The Resource Inventory is also used as input for:
- risk identification
- alternative technology mapping
- scoring *(only in Connected mode)*

## What you will see

Typically, the inventory includes:

- service/resource type (e.g., S3, Lambda, API Gateway)
- number of resources per service type
- location
- totals for the assessed scope
