jdbc:postgresql://rhdh-secret.sonataflow-infra:5432/Sonataflow/currentSchema-sonataflow-platform-data-index-service


1. Task: Deploy and Run DAGs
Description: Set up and execute Directed Acyclic Graphs (DAGs) for migration workflows.
Subtasks:

Configure and deploy ETL DAGs in the target environment.

Validate DAG execution logs for errors.

2. Task: Install and Configure Keycloak
Description: Set up Keycloak for authentication in RHDH.
Subtasks:

Create a new Keycloak subscription in OpenShift.

Deploy Keycloak Helm charts in the cti-evcs-orion-177399 namespace.

Validate Keycloak pod health post-deployment.

3. Task: Deploy Red Hat Developer Hub (RHDH)
Description: Initialize RHDH with fresh DB and plugins.
Subtasks:

Database Setup:

Initialize a fresh PostgreSQL DB for RHDH.

Validate DB permissions and plugin compatibility.

RBAC & Permissions:

Configure Role-Based Access Control (RBAC) in RHDH.

Map existing Backstage permissions to RHDH.

Login & Plugins:

Integrate Keycloak for SSO.

Install and validate required RHDH plugins (TechDocs, Catalog, etc.).

TechDocs Onboarding:

Migrate existing TechDocs content to RHDH.

4. Task: Data Migration
Description: Migrate data from Backstage UAT DB to RHDH DB.
Subtasks:

Preparation:

Identify DB objects to migrate (reuse Andromeda migration list).

Export data from Backstage UAT DB.

Execution:

Import data into RHDH DB, renaming schemas from date to self-service.

For CDS, sync entities via rhdh-entities YAML files in Bitbucket (DEVX repo).

Validation:

Verify data integrity post-migration.

Cross-check schema permissions and relationships.

5. Task: Keycloak Instance Deployment
Description: Configure Keycloak realms for RHDH.
Subtasks:

Create a new Keycloak realm for RHDH.

Set up client roles, users, and identity providers.

Test SSO integration with RHDH.

6. Task: SSL Route Configuration
Description: Secure RHDH and Keycloak with SSL.
Subtasks:

Generate/update SSL certificates for RHDH routes.

Configure OpenShift routes with HTTPS.

Validate SSL handshake and certificate trust chain.

7. Task: Post-Migration Validations
Description: Ensure all components work post-migration.
Subtasks:

Smoke-test RHDH UI, plugins, and search functionality.

Validate Keycloak authentication flows.

Verify TechDocs rendering and catalog entities.

8. Task: Monitoring and Alerts
Description: Set up proactive monitoring.
Subtasks:

Configure database monitoring alerts (e.g., CPU, memory, connection spikes).

Set up alerts for short URL service health.

9. Task: URL Flip (Go-Live)
Description: Redirect traffic from Backstage to RHDH.
Subtasks:

Update DNS/CNAME records to point to RHDH routes.

Communicate the change to stakeholders.

Monitor for post-flip issues.

