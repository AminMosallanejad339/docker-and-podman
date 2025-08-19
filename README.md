# Docker & Podman for Data Engineering

This repository is my personal knowledge base and practice space for learning **Docker** and **Podman** with a focus on **data engineering use cases**.  
It contains notes, examples, Dockerfiles, and mini-projects that I can revisit anytime.

---

## 📂 Repository Structure

```text
docker-data-engineering-notes/
├── README.md                   # Main introduction (this file)
├── concepts/                   # Core concepts and theory
│   ├── docker_basics.md
│   ├── podman_basics.md
│   ├── docker_vs_podman.md
│   └── cheatsheet.md
├── dockerfiles/                # Example Dockerfiles
│   ├── Dockerfile_Guide.md
│   ├── python_app/
│   ├── postgres/
│   └── airflow/
├── compose-examples/           # Docker Compose examples
|   ├── DockerCompose_Guide.md
│   ├── postgres.yml
│   ├── airflow.yml
│   └── kafka_spark.yml
├── mini-projects/              # Hands-on projects for practice
│   ├── 01_docker_postgres/
│   ├── 02_docker_airflow/
│   └── 03_kafka_pipeline/
└── notes/                      # Extra notes and troubleshooting
    ├── networking.md
    ├── volumes.md
    ├── security.md
    └── troubleshooting.md
```

---

##### 🎯 Goals

- Learn **Docker basics** (images, containers, volumes, networks).
- Compare **Docker vs Podman** and understand when to use each.
- Practice **data engineering workflows** using Docker:
  - PostgreSQL in containers
  - Apache Airflow for ETL pipelines
  - Kafka + Spark for streaming
- Build a **personal cheatsheet** for quick reference.
- Document **troubleshooting tips** I encounter along the way.

---

##### 🛠️ Tools Covered

- **Docker**: Core containerization tool.
- **Podman**: Docker alternative, daemonless and rootless.
- **Docker Compose**: Multi-container setup.
- **Data Engineering Tools in Containers**:
  - PostgreSQL
  - Apache Airflow
  - Apache Kafka
  - Apache Spark

---

##### 📖 How to Use

1. Clone this repo:
   ```bash
   git clone https://github.com/<your-username>/docker-data-engineering-notes.git
   cd docker-data-engineering-notes

1. Explore notes in the `concepts/` and `notes/` folders.
2. Run examples from `dockerfiles/` or `compose-examples/`.
3. Try the `mini-projects/` for hands-on practice.

------

## ✅ Status

-  Set up repo structure
-  Add Docker basics notes
-  Add Podman basics notes
-  Create PostgreSQL mini-project
-  Add Airflow mini-project
-  Add Kafka + Spark pipeline

------

## 📌 References

- [Docker Documentation](https://docs.docker.com/)
- [Podman Documentation](https://podman.io/)
- [Awesome Docker](https://github.com/veggiemonk/awesome-docker)
- [Data Engineering Zoomcamp (free course)](https://github.com/DataTalksClub/data-engineering-zoomcamp)

------

✍️ *This repo is a living document. I’ll keep updating it as I learn more about Docker, Podman, and data engineering workflows.*


