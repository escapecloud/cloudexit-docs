# Required permissions

cloudexit requires **read-only** access to discover resources and retrieve cost signals.

If permissions are missing, the most common symptoms are:
- empty or incomplete inventory
- missing cost data
- validation failures during the “Validate permissions” stage

**Minimum required permissions**

| Cloud Provider | Required Permissions |
|--------------|----------------------|
| Microsoft Azure | **Reader** + **Cost Management Reader** |
| Amazon Web Services | **ViewOnlyAccess** + **AWSBillingReadOnlyAccess** |


**Principle of least privilege**

We recommend using least-privilege credentials:
- avoid overly privileged accounts (e.g., Owner/Admin)
- scope access to only the subscriptions / accounts / projects you intend to assess

cloudexit does **not** require write permissions.

**Troubleshooting permission issues**

If assessment fails during:
- **Validate permissions**
- **Build Resource Inventory**
- **Build Cost Inventory**

…double check that the credentials include the required roles/policies above.

Provider-specific guides:
- [AWS permissions](aws.md)
- [Azure permissions](azure.md)
