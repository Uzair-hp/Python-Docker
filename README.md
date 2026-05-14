# Python Docker Dev Example

A modern Python FastAPI application demonstrating a complete Docker development workflow, featuring automated CI/CD with GitHub Actions.

## 🚀 Features

- **FastAPI**: High-performance web framework for building APIs.
- **SQLModel**: Interaction with PostgreSQL using Python objects.
- **Dockerized**: Fully containerized environment using Docker and Docker Compose.
- **CI/CD**: Automated linting, type checking, and Docker image builds via GitHub Actions.
- **Code Quality**: Integrated with `pre-commit`, `Ruff`, and `Pyright`.

## 🛠️ Getting Started

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Git](https://git-scm.com/)

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Uzair-hp/Python-Docker.git
   cd Python-Docker
   ```

2. **Start the application:**
   Use Docker Compose to spin up the FastAPI server and the PostgreSQL database:
   ```bash
   docker compose up --build
   ```

3. **Access the API:**
   - **API Home**: [http://localhost:8001/](http://localhost:8001/)
   - **Interactive Docs (Swagger)**: [http://localhost:8001/docs](http://localhost:8001/docs)

### Database Configuration
The database password is securely managed via Docker Secrets and stored in `db/password.txt`. The application automatically handles table creation on startup.

## 🧪 CI/CD Pipeline

This project uses GitHub Actions to ensure code quality and automate deployments.

### Workflow Steps (`build.yml`):
1. **Lint & Test**: Runs `pre-commit` hooks (Ruff) and `Pyright` for static type checking.
2. **Build & Push**: If tests pass, it builds a Docker image and pushes it to [Docker Hub](https://hub.docker.com/r/ujer01/python-docker).

### Required GitHub Secrets/Variables:
- `vars.DOCKER_USERNAME`: Your Docker Hub ID (e.g., `ujer01`).
- `secrets.DOCKERHUB_TOKEN`: Your Docker Hub Personal Access Token.

## 📦 Docker Image

You can pull the latest production-ready image directly from Docker Hub:

```bash
docker pull ujer01/python-docker:latest
```

## 📜 License

This project is open-source and available under the MIT License.
