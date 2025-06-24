
# 🛠️ DevOps Intern Assignment: Nginx Reverse Proxy + Docker

## 📦 Project Overview

This project demonstrates a Docker-based microservice architecture consisting of:
- A Golang backend service (`service_1`)
- A Python Flask backend service(`service_2`)
- An Nginx reverse proxy to route requests

All services are containerized and orchestrated using Docker Compose. Nginx acts as the entry point and proxies requests based on path prefixes.

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   └── Dockerfile
├── service_1
│   ├── main.go
│   └── Dockerfile
├── service_2
│   ├── app.py
│   ├── pyproject.toml
│   └── Dockerfile
└── README.md
```

---

## 🚀 Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Chebrolupavanapranavi/dpdzero-Assignment.git
cd dpdzero-Assignment
```

### 2. Start the Services
Run the following to build and start all services:
```bash
docker-compose up --build
```

This brings up:
- `service1` on `http://localhost:8080/service1`
- `service2` on `http://localhost:8080/service2`

---

## 🌐 Routing via Nginx

| Route Prefix      | Target Service | Internal Port |
|-------------------|----------------|---------------|
| `/service1/*`     | Golang App     | `8001`        |
| `/service2/*`     | Flask App      | `8002`        |

### Examples
- [http://localhost:8080/service1/ping](http://localhost:8080/service1/ping)
- [http://localhost:8080/service2/hello](http://localhost:8080/service2/hello)

---

## ✅ Features

- 🔄 Reverse proxy routing using path prefixes
- 🩺 Health checks for both services using `/ping` endpoints
- 🧾 Custom logging in Nginx for each request (timestamp + path)
- 🐳 Fully containerized setup

---

## 🛡️ Bonus Implemented

- [x] Docker health checks
- [x] Custom Nginx access logs (`$time_local - $request_uri`)
- [x] Works with one command `docker-compose up --build`

---

## 📝 Notes

- Make sure ports `8001`, `8002`, and `8080` are free before running.
- Nginx logs are viewable using: `docker logs nginx`

---

## 📮 Submission

This project was submitted as part of the DevOps Internship assignment at [DPD Zero](https://dpdzero.com/).
