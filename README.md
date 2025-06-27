jdbc:postgresql://rhdh-secret.sonataflow-infra:5432/Sonataflow/currentSchema-sonataflow-platform-data-index-service
Vendor Collaboration: Direct email correspondence is essential for clarifying technical specifications, sharing certification artifacts, and coordinating validation timelines.

Efficiency: Current communication barriers (e.g., restricted external domains) delay response times, impacting project milestones.

Compliance Assurance: All communications will adhere to corporate security policies, and sensitive data will be shared via approved encrypted channels (e.g., Red Hat Secure Portal or PGP).



I hope you’re doing well. I’m reaching out regarding an urgent issue we’ve encountered with the Red Hat Developer Hub (RHDH) Orchestrator Operator release 1.5.0.

Issue Summary
When attempting to create a Custom Resource (CR) for the SonataFlow Orchestrator Platform, the reconciliation fails if the backstageapi is not pre-existing. The Orchestrator Operator does not create the platform and instead complains about the missing backstage CRD.

Root Cause & Context
This was hard to diagnose initially because our earlier environment (using version 1.0.3) had a pre-existing backstageapi, so we didn’t encounter the issue.

Now, in a new cluster (fresh install of 1.5.0), the Orchestrator Operator fails to proceed unless the backstageapi is manually provisioned first.

We are not installing RHDH via Helm charts or the RHDH Operator, so we need guidance on how to handle this dependency in the current release.

Request for Immediate Assistance
Given that this is blocking new deployments, we’d appreciate:

Confirmation if this is a known issue and if there’s a recommended workaround.

Clarification on whether the Orchestrator Operator should handle the backstageapi dependency automatically (or if manual steps are required).

Any patches or fixes planned for this in the near term.

This is time-sensitive, so we’d greatly appreciate a prompt response or escalation to the appropriate engineering team. Let me know if you need additional details.
