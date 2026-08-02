**Definition**

- Container orchestration platform.
- Manages Docker containers.

**Flow**

```
Docker Image
     ↓
Deployment
     ↓
Pods
     ↓
Service
     ↓
Users
```

**Keywords**

- Pod → Smallest deployable unit
- Deployment → Manages Pods
- Service → Stable endpoint
- Replica → Multiple Pod copies
- Self-healing → Recreates failed Pods
- Auto Scaling → Scale up/down
- Load Balancing → Distributes traffic

**Simple YAML**

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: dotnet-app
spec:
  replicas: 3
```

---

## Interview One-liners

**Docker**

> Packages application + dependencies into a container.

**Kubernetes**

> Manages, scales, load balances, and self-heals Docker containers.

---

## End-to-End Flow

```
Code
 ↓
Git
 ↓
CI/CD
 ↓
Docker Build
 ↓
Docker Image
 ↓
Docker Registry
 ↓
Kubernetes Deployment
 ↓
Pods
 ↓
Service
 ↓
Users
```


### Registry

- Stores Docker images.
- Example: Docker Hub, Amazon ECR.

```
Docker Image → Registry → Kubernetes pulls image
```

---

### Pod

- Smallest deployable unit in Kubernetes.
- Usually contains **one Docker container**.

```
Pod
 └── Container
```

---

### Service

- Provides a **fixed IP/DNS** to access Pods.
- Load balances traffic across Pods.

```
User
  ↓
Service
  ↓
Pod1
Pod2
Pod3
```

### One-line interview answers

- **Registry:** Stores Docker images.
- **Pod:** Smallest deployable unit that runs one or more containers.
- **Service:** Stable endpoint that exposes Pods and load balances requests.