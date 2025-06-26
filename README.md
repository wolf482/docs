opm index add \
  --bundles registry.redhat.io/rhdh/rhdh-operator-bundle:1.5.0 \
  --tag your-registry.example.com/your-namespace/rhdh-index:v1.5.0 \
  --container-tool podman \
  --binary-image registry.redhat.io/openshift4/ose-operator-registry:v4.16
