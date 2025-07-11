# DevOps Nginx Assignment

This project demonstrates how to run two microservices (`service_1` in Go and `service_2` in Python/Flask) behind an Nginx reverse proxy using Docker Compose.

---

## 📁 Project Structure

devops-nginx-assignment/
├── docker-compose.yml
├── nginx/
│ ├── Dockerfile
│ └── nginx.conf
├── service_1/
│ ├── Dockerfile
│ ├── go.mod
│ ├── main.go
├── service_2/
│ ├── Dockerfile
│ ├── app.py
│ └── pyproject.toml

yaml
Copy
Edit

---

## 🚀 Setup Instructions

### Prerequisites
- Docker
- Docker Compose

### Steps to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Abhishek-Soni-Git/devops-nginx-assignment.git
   cd devops-nginx-assignment
Start the containers:

bash
Copy
Edit
docker-compose up --build
Access the services:

http://localhost:8080/ → Proxies to service_2 /ping

http://localhost:8080/service1 → Proxies to service_1 /ping# devops-nginx-assignment




Nginx listens on port 80 (mapped to host 8080).

Routes:

/ → service_2 (Flask app running on port 8002)

/service1 → service_1 (Go app running on port 8001)
