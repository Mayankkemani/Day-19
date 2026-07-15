# 🐳 Day 19 – Dockerfile Basics

## 📖 Overview

Today, I learned how to create my own Docker Images using Dockerfiles. Instead of using pre-built images only, I created custom images and understood how Docker builds images layer by layer.

---

# 📚 Topics Covered

## 🏗️ What is Dockerfile?

A Dockerfile is a text file that contains instructions for building a Docker Image.

### Workflow

Dockerfile → Docker Image → Docker Container

Dockerfile helps automate application deployment and ensures consistency across environments.

---

# 🔥 Dockerfile Instructions Learned

## 1️⃣ FROM

Defines the Base Image.

Example:

```dockerfile
FROM ubuntu
```

Meaning:

Build my custom image on top of Ubuntu.

---

## 2️⃣ RUN

Executes commands during image build.

Example:

```dockerfile
RUN apt update
RUN apt install -y cowsay
```

These commands execute during:

```bash
docker build
```

---

## 3️⃣ CMD

Defines the default command that runs when the container starts.

Example:

```dockerfile
CMD ["echo","Hello Docker"]
```

This command executes during:

```bash
docker run
```

---

# 🧪 First Custom Docker Image

## Dockerfile

```dockerfile
FROM ubuntu

RUN apt update

CMD ["echo","Hello Mayank, My First Docker Image"]
```

### Build Image

```bash
docker build -t my-first-image .
```

### Run Container

```bash
docker run my-first-image
```

### Output

```text
Hello Mayank, My First Docker Image
```

---

# 🐄 Custom Cowsay Image

## Dockerfile

```dockerfile
FROM ubuntu

RUN apt update && apt install -y cowsay

CMD ["/usr/games/cowsay","Welcome Mayank to Docker"]
```

---

### Build Image

```bash
docker build -t my-cow-image .
```

### Run Container

```bash
docker run my-cow-image
```

### Output

```text
 ___________________________
< Welcome Mayank to Docker >
 ---------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

---

# 🐳 Docker Layers

Docker builds images layer by layer.

Example:

```text
FROM ubuntu
      ↓
Layer 1

RUN apt update
      ↓
Layer 2

RUN install cowsay
      ↓
Layer 3

CMD
      ↓
Metadata Layer
```

Docker reuses layers to speed up future builds.

---

# 📌 Important Concepts Learned

## RUN vs CMD

| RUN | CMD |
|------|------|
| Executes during `docker build` | Executes during `docker run` |
| Used for installation/configuration | Used to start the application |

---

## Image vs Container

| Image | Container |
|--------|------------|
| Blueprint | Running Instance |
| Static | Dynamic |
| One Image can create many containers | Executes the application |

---

# 💻 Commands Practiced

```bash
docker build -t my-first-image .

docker run my-first-image

docker build -t my-cow-image .

docker run my-cow-image

docker images

docker image ls
```

---

# 🎯 Key Learning

Today I learned how developers package applications into Docker Images using Dockerfiles.

Dockerfile helps automate:

- Installing dependencies
- Configuring environments
- Building custom images
- Running applications consistently on any system

This is one of the most important concepts in modern DevOps and CI/CD workflows.

---

# 🚀 Outcome

✅ Learned Dockerfile Basics  
✅ Learned FROM instruction  
✅ Learned RUN instruction  
✅ Learned CMD instruction  
✅ Built my first custom Docker Image  
✅ Built a custom Cowsay Image  
✅ Understood Docker Layers and Build Process

---

## 🔥 Next Step

➡️ Day 20 – COPY & WORKDIR

Topics:

- WORKDIR
- COPY
- Developer Code Containerization
- docker exec
- docker logs
- Python Application in Docker

#Docker #DevOps #Dockerfile #Containers #Linux #Cloud #LearningInPublic
