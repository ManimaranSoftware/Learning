**Definition**

- Containerization platform.
- Packages app + dependencies.

**Flow**

```
Code
 ↓
Dockerfile
 ↓
Image
 ↓
Container
```

**Dockerfile**

```
FROM
WORKDIR
COPY
ENTRYPOINT
```

**Commands**

```
docker build -t myapp .
docker run -p 8080:80 myapp
docker ps
docker ps -a
docker stop <id>
```

**Keywords**

- Image → Blueprint
- Container → Running instance
- Dockerfile → Instructions