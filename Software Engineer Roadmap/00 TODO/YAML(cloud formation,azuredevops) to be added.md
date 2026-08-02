
| YAML                    | Purpose                                            |
| ----------------------- | -------------------------------------------------- |
| **CloudFormation YAML** | Creates AWS resources (Lambda, S3, RDS, IAM, etc.) |
| **Azure DevOps YAML**   | Defines CI/CD pipeline (build, test, deploy)       |
| **Docker Compose YAML** | Runs multiple Docker containers together           |
| **Kubernetes YAML**     | Defines Pods, Deployments, Services, etc.          |


## Build Pipeline (`azure-pipelines.yml`)

```
trigger:
- main

pool:
  vmImage: ubuntu-latest

steps:
- task: UseDotNet@2
  inputs:
    version: '8.0.x'

- script: dotnet restore

- script: dotnet build --configuration Release

- script: dotnet test

- script: dotnet publish -c Release -o publish

- task: PublishBuildArtifacts@1
```

---

## Release Pipeline (Concept)

```
stages:

- Build
    ↓

- Deploy Dev
    ↓

- Approval
    ↓

- Deploy QA
    ↓

- Approval
    ↓

- Deploy Production
```

---

## Simple Deployment YAML

```
stages:
- stage: Deploy
  jobs:
  - job: Deploy
    steps:
    - script: echo "Deploying application..."
```

### Interview keywords

- `trigger`
- `pool`
- `steps`
- `restore`
- `build`
- `test`
- `publish`
- `artifact`
- `deploy`
- `approval`
- `rollback`

**Flow:** `Code → Build → Test → Publish Artifact → Deploy Dev → QA → Production`