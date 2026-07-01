# Demo: DevOps-Orchestrator

**User Request:** "Create a basic GitHub Actions workflow file that builds a docker image and deploys to GCP Cloud Run."

---

### pipelines/deployment_pipeline.yml
```yaml
name: Deploy to Cloud Run
on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Authenticate GCP
        uses: google-github-actions/auth@v2
        with:
          workload_identity_provider: 'projects/123/locations/global/workloadIdentityPools/my-pool/providers/my-provider'
          service_account: 'deployer@my-project.iam.gserviceaccount.com'
```
