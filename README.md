# actions
Collection of GitHub actions and workflows

## deploy.yml example
```yaml
on:
  push:
    branches:
      - master
  workflow_dispatch:

name: Deploy to Amazon ECS

jobs:
  build:
    uses:
      ucdavis-lsit/actions/.github/workflows/deploy.yml@main
    with:
      repo: 'ecr-repository-name'
      cluster: 'ecs-cluster-name'
      service: 'ecs-service-name'
    secrets:
      access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      secret-access-key: $${{ secrets.AWS_SECRET_ACCESS_KEY }}
```
