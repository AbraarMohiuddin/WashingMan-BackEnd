# Washing Man Backend

This is the backend service for the **Washing Man Kiosk App**, built with **Node.js** and **Express.js**. The backend is containerized using Docker and provides APIs for managing laundromat machines and transactions.

## 🚀 Features
- Fetch available machines and their statuses.
- Start a machine and simulate transactions.
- Fully containerized with Docker and Docker Compose.

---

## 🛠 Prerequisites

Ensure you have the following installed on your system:

- [Docker](https://www.docker.com/get-started) (Make sure it is running)
- [Git](https://git-scm.com/downloads)

---

## 📥 Clone the Repository

git clone https://github.com/AbraarMohiuddin/WashingMan-BackEnd.git
cd WashingMan-BackEnd

## 🐳 Running the Backend with Docker

### Option 1: Using Docker CLI

Manually build and run the container:

docker build -t washing-man-backend .
docker run -p 3000:3000 washing-man-backend

This will:

1. Build the Docker image.
2. Run the container, exposing it on port 3000.

### Option 2: Using Docker Compose (Recommended)

For an easier setup, use Docker Compose:

docker-compose up --build

To stop the container:

docker-compose down

---

## 🛠 API Endpoints

Once the backend is running, you can test the API endpoints using:

### 🔍 Get All Machines
URL: GET /machines  
Description: Fetches the list of all washing machines.

Test via Curl:
curl http://localhost:3000/machines

Test via Browser:
http://localhost:3000/machines

---

### 🔍 Get a Single Machine
URL: GET /machines/:id  
Description: Fetch details for a specific machine.

Test via Curl:
curl http://localhost:3000/machines/1

---

### 💰 Start a Machine/Simulate a Transaction
URL: POST /transactions  
Description: Simulates a payment and marks a machine as "In Use".

Test via Curl:
curl -X POST http://localhost:3000/transaction -H "Content-Type: application/json" -d '{"machineId": 1}'

---

## 🏗 Deployment Instructions

### Pushing to GitHub

If you've made changes, push them to GitHub:

git add .
git commit -m "Updated backend with Docker setup"
git push origin main

### Setting Up CI/CD

This repository includes GitHub Actions for automatically building and pushing the Docker image to Docker Hub. To enable this:

1. Set up a Docker Hub account.
2. Go to GitHub Repo → Settings → Secrets → Actions.
3. Add:
   - DOCKER_HUB_USERNAME
   - DOCKER_HUB_ACCESS_TOKEN (Generate from Docker Hub Security settings)

Once set up, every git push to main will automatically:
1. Build the Docker image.
2. Push it to Docker Hub.

---

## ❓ Troubleshooting

### Common Issues

- Docker not running?
  - Ensure Docker Desktop is installed and running.
  - Restart Docker and retry.

- Port 3000 already in use?
  - Run: docker ps to check running containers.
  - Stop conflicting containers: docker stop <container_id>.

- Docker build fails?
  - Run: docker system prune -a to clear cache and try again.

---

## 📜 License
This project is licensed under the MIT License.

---

## 👨‍💻 Author
Developed by Abraar Mohiuddin 🚀

