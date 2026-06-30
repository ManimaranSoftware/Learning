### Kubernetes (K8s)

- Kubernetes - Container orchestration platform.
- Automates deployment, scaling and management of containers.

---

### Cluster

- Cluster - Collection of nodes managed by Kubernetes.

---

### Node

- Node - Machine (physical or virtual) that runs application containers.

---

### Master Node (Control Plane)

- Manages the Kubernetes cluster.
- Schedules workloads and monitors cluster state.

---

### Worker Node

- Runs application Pods.
- Executes workloads assigned by the Control Plane.

---

### Pod

- Pod - Smallest deployable unit in Kubernetes.
- Contains one or more containers.

---

### Deployment

- Deployment - Manages Pods and ensures the desired number of replicas are running.

---

### ReplicaSet

- ReplicaSet - Maintains the required number of Pod replicas.

---

### Service

- Service - Provides a stable endpoint to access Pods.
- Enables communication between applications.

---

### Namespace

- Namespace - Logically separates resources within a Kubernetes cluster.

---

### ConfigMap

- ConfigMap - Stores non-sensitive configuration data.

---

### Secret

- Secret - Securely stores sensitive information.
- Examples - Passwords, API Keys, Connection Strings.

---

### Ingress

- Ingress - Manages external HTTP/HTTPS access to services.

---

### Horizontal Pod Autoscaler (HPA)

- Automatically increases or decreases the number of Pods based on workload.

---

### Rolling Update

- Updates application Pods gradually without downtime.

---

### Self-Healing

- Automatically restarts or replaces failed Pods.
- Ensures application availability.

---

### Benefits

- Automated deployment.
- High availability.
- Automatic scaling.
- Self-healing.
- Efficient container management.

---

## Small improvement 💡

Let's also add:

### Kubernetes vs Docker

- **Docker** → Creates and runs containers.
- **Kubernetes** → Manages and orchestrates containers at scale.