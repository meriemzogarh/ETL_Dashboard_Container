# ETL Dashboard (Dockerized)

This repository contains only the **Docker Compose setup** required to run the ETL Dashboard project.  
The application is prebuilt and published to **Docker Hub**, so you don’t need to clone the source code or build images locally.

---

## 🚀 Quick Start

1. **Install prerequisites**:
   - [Docker](https://docs.docker.com/get-docker/)
    - [Git](https://git-scm.com/downloads)

2. **Clone this repo**:

   ```bash
   git clone https://github.com/meriemzogarh/ETL_Dashboard_Container.git
   cd etl-dashboard-docker
   ````

## 🐳 Docker Hub Images

Both services are published to Docker Hub under the namespace **meriemzogarh**:

* **Backend**: [meriemzogarh/yazaki_etl_dashboard_backend:latest](https://hub.docker.com/r/meriemzogarh/yazaki_etl_dashboard_backend)
* **Frontend**: [meriemzogarh/yazaki_etl_dashboard_frontend:latest](https://hub.docker.com/r/meriemzogarh/yazaki_etl_dashboard_frontend)

3. **If you want to pull them manually:**

   ```bash
   docker pull meriemzogarh/yazaki_etl_dashboard_backend:latest
   docker pull meriemzogarh/yazaki_etl_dashboard_frontend:latest
   ```

4. **Start the containers:**

   ```bash
   docker-compose pull
   docker-compose up -d
   ```

5. **Access the apps:**

   * Frontend (Flask) → [http://localhost:3000](http://localhost:3000)
   * Backend (FastAPI) → [http://localhost:8000](http://localhost:8000)

---

## ⚙️ Configuration

* Containers are connected via a custom Docker network (`etl-network`).
* Named volume `etl_data` is used to persist data inside the containers.
* Health checks are enabled to ensure services are running.
* Default environment variables are defined in the `docker-compose.yml`.
  Update them if you need custom ports or paths.

---

## 🔖 Versioning

Images are tagged with `latest` for convenience.
For stability in production, you can also use versioned tags (e.g., `v1.0.0`) if available:

```yaml
services:
  backend:
    image: meriemzogarh/etl_dashboard-backend:v1.0.0
  frontend:
    image: meriemzogarh/etl_dashboard-frontend:v1.0.0
```

---

## 👩‍💻 Contributing

This repo is for container orchestration only.
If you need to modify backend/frontend code, please refer to the main project repository.

---

## 📜 License
This repository and its contents are private and proprietary.
Unauthorized copying, modification, distribution, or use is strictly prohibited.
