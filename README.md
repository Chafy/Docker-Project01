# Docker-Project01
Hands-on Docker project: Deploying a simple HTML web page using Nginx with port mapping and host volumes.

```markdown
# Project 1: Deploying a Simple HTML Web Page Using Nginx

A hands-on DevOps project demonstrating how to containerize a static HTML webpage using Docker, manage network ports, and leverage host volumes for real-time code updates.

## 🚀 Overview
This project showcases the fundamentals of working with Docker containers. Instead of rebuilding an image every time a code change is made, this setup utilizes **Bind Mounts (Host Volumes)** to allow instant, live updates directly from the host machine to the running container.

## 🛠️ Tech Stack
* **Containerization:** Docker
* **Web Server:** Nginx (Official Alpine/Latest image)
* **OS:** Ubuntu (Host)

---

## ⚙️ How It Works & Key Configurations

When running the container, specific flags are used to solve common containerization hurdles:

1. **Port Mapping (`-p 8080:80`)**
   * *Problem:* Containers run in an isolated network environment.
   * *Solution:* Maps port `8080` on your host machine to port `80` inside the Nginx container, allowing you to view the webpage locally in your browser.

2. **Host Volumes / Bind Mounts (`-v ...`)**
   * *Problem:* Constantly rebuilding or jumping inside containers to change code is inefficient.
   * *Solution:* Mounts your local project directory directly to Nginx's web root directory inside the container. 

---

## 🏃‍♂️ Getting Started

### Prerequisites
Make sure you have Docker installed and running on your system.

### Running the Container
Execute the following `docker run` command in your terminal (adjust the local path to match your environment):

```bash
docker run -it -d \
  --name project01 \
  -p 8080:80 \
  -v /home/ubuntu/project:/usr/share/nginx/html \
  nginx

```

### Accessing the Web Page

Open your browser and navigate to:

```text
http://localhost:8080

```

### Instant Edit Feature

Because of the bind mount (`-v`), any edits you make to your HTML files inside `/home/ubuntu/project` on your host machine will instantly reflect in the browser upon refreshing—**no container restart required!**

---

## 📦 Series Context

This is **Project 1 of 3** in a containerization hands-on mini-series:

* **Project 1:** Deploying a Simple HTML Web Page Using Nginx *(Current)*
* **Project 2:** Deploying a Simple Website Using Nginx
* **Project 3:** Multi-Container Deployment Using Docker Compose (Flask + Redis)

