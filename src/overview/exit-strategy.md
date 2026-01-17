# Exit Strategy

cloudexit supports multiple **exit strategies** as part of the cloud exit readiness assessment.

An exit strategy describes the target scenario you are planning for (for example, moving repatriating workloads on-premises vs migrating to another cloud provider). The selected strategy helps cloudexit interpret findings and frame recommendations based on a realistic exit path.

In configuration files, this is represented as `exitStrategy`.

**Supported Exit Strategies**

| Strategy | Value |
|---------|------:|
| Repatriation to On-Premises | 1 |
| Hybrid Cloud Adoption | TBD |
| Migration to Alternate Cloud | 3 |


**Choose Exit Strategy**

If you are unsure which one to choose, start with the strategy that reflects your most likely exit plan:

- Choose **Repatriation to On-Premises (1)** if you expect to move workloads back to your own infrastructure.
- Choose **Migration to Alternate Cloud (3)** if you expect to migrate to a different cloud provider.

> **Note:** `Hybrid Cloud Adoption` may be added in the future.

**Why it's important?**

The exit strategy impacts how cloudexit evaluates:

- which services are likely to become blockers in an exit scenario
- portability constraints and dependencies
- the relevance of alternative technologies
- the overall framing of the exit readiness assessment

In other words: it helps translate technical findings into a more realistic exit plan.
