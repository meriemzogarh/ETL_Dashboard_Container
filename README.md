# ETL Dashboard (Dockerized)

This repository contains only the **Docker Compose setup** required to run the ETL Dashboard project.  
The application is prebuilt and published to **Docker Hub**, so you don’t need to clone the source code or build images locally.

---

## 🚀 Quick Start

1. **Install prerequisites**:
   - [Docker](https://docs.docker.com/get-docker/)
   - [Docker Compose](https://docs.docker.com/compose/install/)

2. **Clone this repo**:

   ```bash
   git clone https://github.com/meriemzogarh/ETL_Dashboard_Container.git
   cd etl-dashboard-docker
   ````

3. **Platform support (already included)**:
   This repository includes a `docker-compose.override.yml` file to ensure compatibility with most platforms.

   * It specifies the `linux/amd64` platform for backend and frontend containers.
   * This helps avoid errors on systems with x86_64 CPUs (e.g., most Windows and Linux laptops).
   * It does **not affect ARM users** (like Mac M1/M2) — Docker will auto-detect the right platform.

---

## 🐳 Docker Hub Images

Both services are published to Docker Hub under the namespace **meriemzogarh**:

* **Backend**: [meriemzogarh/etl_dashboard-backend:latest](https://hub.docker.com/r/meriemzogarh/etl_dashboard-backend)
* **Frontend**: [meriemzogarh/etl_dashboard-frontend:latest](https://hub.docker.com/r/meriemzogarh/etl_dashboard-frontend)

4. **If you want to pull them manually:**

   ```bash
   docker pull meriemzogarh/etl_dashboard-backend:latest
   docker pull meriemzogarh/etl_dashboard-frontend:latest
   ```

5. **Start the containers (with override applied by default):**

   ```bash
   docker-compose pull
   docker-compose up -d
   ```

6. **(Optional)**: If you **don't want to use** the override file (e.g., you're on an ARM/Mac system and prefer Docker to auto-detect), you can run Docker Compose with just the base file:

   ```bash
   docker-compose -f docker-compose.yml up -d
   ```

   > This will ignore the `docker-compose.override.yml` and use only the settings from `docker-compose.yml`.

7. **Access the apps:**

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

## 🧩 Platform Compatibility

This project supports both `amd64` (Intel/AMD CPUs) and `arm64` (Apple Silicon) platforms.

To avoid platform mismatch errors, the included `docker-compose.override.yml` file explicitly sets:

```yaml
services:
  backend:
    platform: linux/amd64
  frontend:
    platform: linux/amd64
```

This override is automatically used on most systems and **only applies locally**, so it won’t affect production deployments or Mac users.

If you're using a Mac (M1/M2), Docker will still use the appropriate `arm64` images unless you override it manually.

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

```
