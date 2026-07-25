## 1. What is Docker?

### Interview Answer

> Docker is a containerization platform used to package an application along with its dependencies so that it runs consistently across different environments.

---

## Memory Tip

> **Docker = Package + Run Anywhere**

---

# 2. Why Docker?

Without Docker:

```
Developer PC
     ✓

Testing Server
     ❌

Production
     ❌
```

Different environments cause issues.

With Docker:

```
Application
+
Runtime
+
Libraries
+
Dependencies

↓

Docker Image

↓

Runs the same everywhere
```

---

## Memory Tip

> **Build Once, Run Anywhere**

---

# 3. What is a Container?

A container is a **running instance of a Docker Image**.

Think of it like this:

```
Dockerfile
     ↓
Docker Image
     ↓
Docker Container
```

---

## Memory Tip

**Image = Blueprint**

**Container = Running Application**

---

# 4. Docker Image

An Image is a read-only template.

Contains:

- Application
- .NET Runtime
- DLLs
- Libraries
- Configuration

---

Example:

```
ASP.NET Core API

↓

Docker Image

↓

Run Anywhere
```

---

## Memory Tip

Image = Template

---

# 5. Docker Container

Container = Running Image

Example

```
Image

↓

Container 1

Container 2

Container 3
```

One image can create many containers.

---

## Memory Tip

Image → Many Containers

---

# 6. Dockerfile

A Dockerfile contains instructions to build an image.

Example:

```
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY . .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

---

### Interview Answer

> A Dockerfile is a text file containing instructions used to build a Docker image.

---

## Memory Tip

Dockerfile = Recipe

---

# 7. Docker Hub

Docker Hub is a repository for Docker images.

Example:

```
docker pull nginx
```

Downloads the Nginx image.

---

## Memory Tip

Docker Hub = GitHub for Images

---

# 8. Docker Commands

### Pull Image

```
docker pull nginx
```

---

### Build Image

```
docker build -t invoice-api .
```

---

### Run Container

```
docker run invoice-api
```

---

### List Containers

```
docker ps
```

---

### Stop Container

```
docker stop <container-id>
```

---

### List Images

```
docker images
```

---

### Remove Container

```
docker rm <container-id>
```

---

### Remove Image

```
docker rmi <image-id>
```

---

# Memory Tip

- pull → Download
- build → Create Image
- run → Start Container
- ps → Running Containers
- images → Available Images

---

# 9. Why Docker for .NET?

Example:

```
.NET API

↓

Docker Image

↓

QA

↓

UAT

↓

Production
```

The same image is deployed everywhere.

---

# 10. Benefits

- Same environment everywhere
- Fast deployment
- Lightweight
- Easy scaling
- Easy rollback
- Better resource utilization than traditional virtual machines

---

# 11. Docker vs Virtual Machine

|Docker|Virtual Machine|
|---|---|
|Lightweight|Heavy|
|Shares host OS kernel|Includes full guest OS|
|Starts in seconds|Takes longer to boot|
|Lower resource usage|Higher resource usage|

---

## Memory Tip

Docker = Container

VM = Full Operating System

---

# 12. Project Example

A good interview answer:

> "We containerized our ASP.NET Core Web API using Docker. The image contained the application and its dependencies, ensuring the same behavior across development, testing, and production environments."

If you **didn't actually use Docker** in your project, don't claim you did. Instead, say:

> "I have hands-on experience creating Docker images for ASP.NET Core applications in practice environments. In my recent project, deployment was handled through our organization's CI/CD pipeline, but I understand how Docker packages applications for consistent deployments."

That's an honest and credible answer.

---

# 13. Common Interview Questions

### Q1. What is Docker?

> A containerization platform.

---

### Q2. What is a Container?

> A running instance of a Docker image.

---

### Q3. What is an Image?

> A read-only template used to create containers.

---

### Q4. What is Dockerfile?

> A file containing instructions to build a Docker image.

---

### Q5. Difference between Image and Container?

**Image**

- Template
- Read-only

**Container**

- Running instance
- Executable

---

### Q6. Why Docker?

> To ensure applications run consistently across different environments.

---

### Q7. What is Docker Hub?

> A public repository for Docker images.

---

### Q8. Can one image create multiple containers?

✅ Yes.

---

### Q9. Docker vs VM?

Docker shares the host OS kernel, while a virtual machine runs its own guest operating system.

---

### Q10. How is Docker useful in CI/CD?

> CI/CD pipelines build a Docker image once, test it, and deploy the same image across environments, ensuring consistency.

---

# Memory Tricks

- Docker → Package & Run Anywhere
- Dockerfile → Recipe
- Image → Blueprint
- Container → Running App
- Docker Hub → Image Repository
- Build Once → Run Anywhere

---

# 🎯 10-Second Recall

> **Docker → Dockerfile → Image → Container → Docker Hub → Build → Run → CI/CD**

---

# 🚀 60-Second Revision

**Docker**

- Containerization platform that packages an application with its dependencies.

**Dockerfile**

- Recipe to build a Docker image.

**Image**

- Read-only template.

**Container**

- Running instance of an image.

**Docker Hub**

- Repository for Docker images.

**Benefits**

- Consistent environments.
- Fast deployment.
- Lightweight.
- Easy scaling.

**Key Commands**

- `docker pull`
- `docker build`
- `docker run`
- `docker ps`

**Project Relevance**

- Commonly used to package ASP.NET Core APIs for deployment through CI/CD pipelines.

---

## ⭐ Interview Tip

If you're asked:

> **"Explain Docker in one minute."**

You can say:

> "Docker is a containerization platform that packages an application with all its dependencies into a Docker image. That image can be run as a container, ensuring the application behaves the same across development, testing, and production environments. In .NET projects, Docker is commonly used with CI/CD pipelines to simplify deployments and improve consistency."

This level of Docker knowledge is more than sufficient for most **4–5 years experienced .NET Backend Developer** interviews unless the role specifically emphasizes DevOps or Kubernetes.