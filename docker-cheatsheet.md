# 🐳 Docker Cheat Sheet (Interview-Focused)

## 🔹 1. Basic Info Commands (very common questions)

```bash
docker version
docker info
docker --help
```

👉 Used to verify installation and environment details.

---

## 🔹 2. Images (Core Concept)

### List images

```bash
docker images
```

### Pull image

```bash
docker pull nginx
```

### Remove image

```bash
docker rmi nginx
```

### Build image

```bash
docker build -t myapp:1.0 .
```

👉 Interview tip:
Be ready to explain **Dockerfile → Image → Container flow**

---

## 🔹 3. Containers (MOST IMPORTANT)

### Run container

```bash
docker run -d -p 80:80 --name mynginx nginx
```

👉 Explanation:

* `-d` → detached mode
* `-p` → port mapping
* `--name` → container name

---

### List containers

```bash
docker ps        # running
docker ps -a     # all
```

---

### Stop / Start

```bash
docker stop mynginx
docker start mynginx
```

---

### Remove container

```bash
docker rm mynginx
```

---

### Execute inside container

```bash
docker exec -it mynginx /bin/bash
```

👉 VERY frequently asked in interviews

---

### Logs

```bash
docker logs mynginx
```

---

## 🔹 4. Volumes (Data Persistence)

### Create volume

```bash
docker volume create myvolume
```

### List volumes

```bash
docker volume ls
```

### Use volume

```bash
docker run -d -v myvolume:/data nginx
```

👉 Interview question:
**“What happens to data when container is deleted?”**

---

## 🔹 5. Networks

### List networks

```bash
docker network ls
```

### Create network

```bash
docker network create mynetwork
```

### Run container in network

```bash
docker run -d --network mynetwork nginx
```

👉 Used in multi-container communication

---

## 🔹 6. Docker System Cleanup

```bash
docker system df
docker system prune
```

👉 Real-world usage: freeing disk space

---

## 🔹 7. Inspect & Debug

### Inspect container/image

```bash
docker inspect mynginx
```

### Resource usage

```bash
docker stats
```

👉 Helps in debugging performance issues

---

## 🔹 8. Save & Load Images

```bash
docker save -o myimage.tar myapp:1.0
docker load -i myimage.tar
```

👉 Asked in scenarios without internet / offline environments

---

## 🔹 9. Tag & Push (Registry)

```bash
docker tag myapp:1.0 myrepo/myapp:1.0
docker push myrepo/myapp:1.0
```

---

## 🔹 10. Docker Compose (Important for interviews)

```bash
docker-compose up -d
docker-compose down
```

👉 Be ready to explain:

* multi-container apps
* YAML structure

---

# 🔥 Most Asked Interview Commands (Focus These)

If you’re short on time, master these:

```bash
docker run
docker ps
docker exec
docker logs
docker build
docker images
docker stop / rm
docker volume
docker network
```

---

# 🧠 Pro Interview Tips (This will differentiate you)

Instead of saying:
❌ “docker run starts container”

Say:
✅ “docker run creates and starts a container from an image, and we can configure networking, volumes, and environment variables at runtime”

---

