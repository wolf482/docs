jdbc:postgresql://rhdh-secret.sonataflow-infra:5432/Sonataflow/currentSchema-sonataflow-platform-data-index-service


Migration Plan as a Scrum Master
Objective:
Break down the provided steps into actionable Jira tasks and subtasks for the team to execute in a sprint.

Jira Tasks and Subtasks
1. Task: Openshift Quotas and Resources Adjustment
Description: Adjust resource quotas for the UAT environment.
Subtasks:

Adjust storage quota by +156B.

Adjust CPU quota by +3cpu.

Adjust memory quota by +106B.

Increase pod limit by +9.

2. Task: Database Setup for RHDH on UAT PostgreSQL
Description: Prepare the database for RHDH in the UAT environment.
Subtasks:

Create an empty database for RHDH on UAT PostgreSQL.

Create required DB roles and schemas (including Keycloak schema).

Collaborate with DBA team to assess filesystem size requirements.

3. Task: Secrets Management for UAT
Description: Consolidate and manage secrets for RHDH UAT.
Subtasks:

Consolidate existing Orion UAT secrets with RHDH-specific secrets.

Create and store secrets for UAT in HC Vault.

4. Task: RHDH Helm Charts Configuration
Description: Update and optimize Helm charts for RHDH UAT deployment.
Subtasks:

Update SSL SAN certificates in Helm charts.

Create and optimize uat/values.yaml for RHDH.

Consolidate RBAC config maps.

Remove hardcoded values from configurations.

Configure liveness probes.

Ensure app-config.yaml and plugins release versions match the release.

Sync entities' timing configurations.

5. Task: ETL Setup for RHDH UAT
Description: Prepare ETL pipelines for RHDH UAT.
Subtasks:

Create new repositories for ETL entities.

Deploy and validate DAGs for ETL processes.

6. Task: Keycloak Helm Charts Deployment
Description: Deploy and configure Keycloak for UAT.
Subtasks:

Prepare UAT Helm chart for Keycloak instance.

Update SSL SAN certificates in Keycloak configurations.
