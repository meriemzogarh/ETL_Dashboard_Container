# ETL Dashboard (Dockerized)

This repository contains only the **Docker Compose setup** required to run the ETL Dashboard project.  
The application is prebuilt and published to **Docker Hub**, so you don’t need to clone the source code or build images locally.

---

## 🚀 Quick Start

1. **Install prerequisites**:
   - [Docker](https://docs.docker.com/get-docker/)
   - [Docker Compose](https://docs.docker.com/compose/install/)

2. **Clone this repo** (only the `docker-compose.yml` lives here):

   ```bash
   git clone https://github.com/<your-org-or-username>/etl-dashboard-docker.git
   cd etl-dashboard-docker

### 🐳 Docker Hub Images

Both services are published to Docker Hub under the namespace **meriemzogarh**:

Backend: [meriemzogarh/etl_dashboard-backend:latest](https://hub.docker.com/r/meriemzogarh/etl_dashboard-backend)

Frontend: [meriemzogarh/etl_dashboard-frontend:latest](https://hub.docker.com/r/meriemzogarh/etl_dashboard-frontend)

3. **If you want to pull them manually:**

   ```bash
   docker pull meriemzogarh/etl_dashboard-backend:latest
   docker pull meriemzogarh/etl_dashboard-frontend:latest

4. **Start the containers:**

   ```bash
   docker-compose pull    # pulls the latest images from Docker Hub
   docker-compose up -d   # runs containers in the background


5. **Access the apps:**

Frontend → http://localhost:3000

Backend (FastAPI) → http://localhost:8000


## ⚙️ Configuration

- Containers are connected via a custom Docker network (etl-network).

- Named volume etl_data is used to persist data inside the containers.

- Health checks are enabled to ensure services are running.

- Default environment variables are defined in the docker-compose.yml.
  Update them if you need custom ports or paths.


## 🔖 Versioning

Images are tagged with latest for convenience.
For stability in production, you can also use versioned tags (e.g., v1.0.0) if available:
```bash
    services:
     backend:
      image: meriemzogarh/etl_dashboard-backend:v1.0.0
     frontend:
      image: meriemzogarh/etl_dashboard-frontend:v1.0.0

---

## 👩‍💻 Contributing

This repo is for container orchestration only.
If you need to modify backend/frontend code, please refer to the main project repository.

## 📜 License

This repository and its contents are private and proprietary.
Unauthorized copying, modification, distribution, or use is strictly prohibited.
