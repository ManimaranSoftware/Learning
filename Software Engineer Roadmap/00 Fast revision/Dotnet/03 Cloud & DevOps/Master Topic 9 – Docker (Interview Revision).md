## Docker Basics
- Containerization Platform
- Packages Application + Dependencies
- Lightweight
- Portable
- Consistent Across Environments

> [!tip]
> **Memory Tip:** Docker = "Runs the Same Everywhere"

---

## Virtual Machine vs Docker
- VM → Includes Guest OS
- Docker → Shares Host OS Kernel
- VM → Heavy
- Docker → Lightweight
- VM → Slow Startup
- Docker → Fast Startup

> [!tip]
> **Memory Tip:** VM = House | Docker = Apartment

---

## Docker Architecture
- Docker Client
- Docker Daemon
- Docker Engine
- Docker Registry
- Docker Hub

---

## Image
- Blueprint for Container
- Read Only
- Built using `Dockerfile`
- Versioned using Tags

---

## Container
- Running Instance of an Image
- Isolated Process
- Lightweight
- Can Start/Stop/Delete

---

## `Dockerfile`
- Defines Image
- Uses Instructions
- Common Instructions:
  - `FROM`
  - `WORKDIR`
  - `COPY`
  - `RUN`
  - `EXPOSE`
  - `ENTRYPOINT`
  - `CMD`

> [!tip]
> **Memory Tip:** Dockerfile = Recipe | Image = Cake | Container = Slice

---

## Docker Commands
- `docker build`
- `docker run`
- `docker ps`
- `docker images`
- `docker stop`
- `docker start`
- `docker rm`
- `docker rmi`
- `docker logs`

---

## Volumes
- Persistent Storage
- Data Survives Container Deletion
- Share Data Between Containers

---

## Networking
- Bridge Network
- Host Network
- Overlay Network
- Container Communication
- Port Mapping using `-p`

---

## Environment Variables
- Store Configuration
- Avoid Hardcoding
- Pass using `-e`
- Useful for Secrets & Settings

---

## Docker Compose
- Manage Multiple Containers
- Uses `docker-compose.yml`
- One Command Startup
- Defines Services
- Defines Networks
- Defines Volumes

> [!tip]
> **Memory Tip:** Compose = Run Entire Application Stack

---

## Multi-Stage Build
- Smaller Images
- Separate Build & Runtime
- Faster Deployment
- Improved Security

---

## Best Practices
- Small Base Images
- Use Multi-Stage Builds
- One Process per Container
- Don't Store Secrets in Images
- Use Volumes for Persistent Data
- Tag Images Properly

---

## Docker in .NET
- Containerize ASP.NET Core APIs
- Deploy to AWS / Azure / Kubernetes
- Consistent Development & Production
- Easy Scaling

---

## Interview Traps
- Image vs Container
- Docker vs Virtual Machine
- `CMD` vs `ENTRYPOINT`
- Volume vs Bind Mount
- `COPY` vs `ADD`
- Docker Compose vs Dockerfile
- Container Restart vs Image Rebuild
- Stateless Container vs Persistent Data

---

## 30-Second Revision Formula

Docker Basics → VM vs Docker → Architecture → Image → Container → `Dockerfile` → Commands → Volumes → Networking → Environment Variables → Docker Compose → Multi-Stage Build → Best Practices → .NET Integration