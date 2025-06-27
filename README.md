# Install JFrog CLI first
# https://jfrog.com/getcli/

# Configure Artifactory
jfrog rt c artifactory-server --url=https://docker-cto-dev-local.artifactrepository.citigroup.net --user=<username> --password=<password>

# Search for Docker images
jfrog rt s "cti-orion-177398/rhdh-hub-rh*"

# List all Docker repositories
jfrog rt curl "/api/docker/<repo-key>/v2/_catalog"

# Get image manifest
jfrog rt curl "/api/docker/<repo-key>/v2/<image>/manifests/<tag>"
