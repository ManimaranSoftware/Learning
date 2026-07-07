Note : commands are not added can be added later
### Docker

- Docker - Containerization platform for building, packaging and running applications.

---

### Container

- Container - Lightweight, isolated runtime environment.
- Includes application and its dependencies.

---

### Image

- Image - Read-only template used to create containers.

---

### Dockerfile

- Dockerfile - Configuration file containing instructions to build a Docker Image.

---

### Docker Engine

- Docker Engine - Core service that builds and runs containers.

---

### Docker Hub

- Docker Hub - Public registry for storing and sharing Docker Images.

---

### Docker Registry

- Docker Registry - Repository for storing Docker Images.
- Can be public or private.

---

### Docker Compose

- Docker Compose - Tool for running multiple containers using a single configuration file.

---

### Volume

- Volume - Persistent storage for containers.
- Data remains even if the container is removed.

---

### Network

- Docker Network - Enables communication between containers.

---

### Port Mapping

- Maps a container port to a host machine port.
- Example: `8080:80`

---

### Container Lifecycle

- Create
- Start
- Stop
- Restart
- Remove

---

### Stateless Container

- Containers should ideally be stateless.
- Persistent data should be stored externally.

---

### Benefits

- Consistent environments.
- Faster deployments.
- Lightweight virtualization.
- Easy scalability.
- Improved portability.

---

## Small improvement 💡

Let's also add:

### Docker vs Virtual Machine

- **Docker** → Shares the host OS kernel, lightweight, starts quickly.
- **Virtual Machine** → Includes a full guest OS, heavier, slower to start.