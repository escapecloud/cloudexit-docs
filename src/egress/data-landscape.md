# Data Landscape

The Data Landscape explains how much data was identified in the assessed scope and where that data currently sits.

**Azure coverage**

The Azure assessment scope is the selected resource group:

| Type | Method | Caveat |
|---|---|---|
| Storage Accounts | Azure Monitor `UsedCapacity` and `BlobCapacity`, split by access tier | Metrics update roughly daily |
| Managed Disks, Snapshots | Provisioned `diskSizeGB` | Allocated size is an upper bound |
| SQL Databases | Monitor `storage` metric | |
| Cosmos DB | `DataUsage` + `IndexUsage` metrics | |
| PostgreSQL Flexible Server | `storage_used` metric | |
| MySQL Flexible Server | `storage_used` metric | |
| Recovery Services Vaults | Not sized | Recovery points cannot be exported from Azure |


**AWS coverage**

The AWS assessment scope is the selected region:

| Type | Method | Caveat |
|---|---|---|
| S3 Buckets | CloudWatch `BucketSizeBytes` per `StorageType` | Metrics can lag by up to roughly 48 hours |
| EBS Volumes, Snapshots | Provisioned size | Upper bound; snapshots can over-count shared blocks |
| RDS Instances | Allocated minus `FreeStorageSpace`, falling back to allocated | Aurora is not sized |
| DynamoDB Tables | `TableSizeBytes` plus index sizes | |
| AWS Backup Vaults | Not sized | Recovery points cannot be exported |
