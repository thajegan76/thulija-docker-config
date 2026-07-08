# Thulija Docker Configuration

This repository contains the official Docker development environment configuration used by Thulija Technology.

The purpose of this repository is to provide a standardized, reproducible, and maintainable development environment for all developers. It contains the Docker configuration required to build and run the two core Thulija software ecosystems.

- **Thulija Platform** – Java, Spring Boot, Angular and MySQL development environment.
- **Thulija Workspace** – PHP, Laravel, Angular, Ionic and MySQL development environment.

The Docker configuration is maintained separately from the application source code so that updates to the development environment can be distributed independently without rebuilding or redistributing the Golden Ubuntu WSL image.

---

# Repository Structure

```
thulija-docker-config
│
├── thulijaplatform
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .devcontainer
│       └── devcontainer.json
│
└── thulijaworkspace
    ├── Dockerfile
    ├── docker-compose.yml
    └── .devcontainer
        └── devcontainer.json
```

---

# Technology Stack

## Thulija Platform

- Ubuntu 24.04
- Java 21
- Spring Boot
- Maven
- Node.js 22
- Angular CLI
- MySQL 8.4
- Docker Desktop
- Visual Studio Code Dev Containers

### Development Ports

| Service | Port |
|----------|-----:|
| Angular | 4200 |
| Spring Boot | 8888 |
| MySQL | 3306 |

---

## Thulija Workspace

- Ubuntu 24.04
- PHP
- Laravel
- Composer
- Node.js 22
- Angular CLI
- Ionic CLI
- MySQL 8.4
- Docker Desktop
- Visual Studio Code Dev Containers

### Development Ports

| Service | Port |
|----------|-----:|
| Angular | 4200 |
| Ionic | 8100 |
| Laravel | 8000 |
| MySQL | 3306 |

---

# Prerequisites

- Windows 11
- Windows Subsystem for Linux (WSL2)
- Ubuntu 24.04
- Docker Desktop
- Visual Studio Code

---

# Usage

Navigate to the required project configuration.

## Thulija Platform

```bash
cd thulijaplatform
docker compose up -d
```

## Thulija Workspace

```bash
cd thulijaworkspace
docker compose up -d
```

---

# Maintenance

This repository is maintained by the Thulija Technology engineering team.

Updates to Docker images, runtime versions, development tools, and Visual Studio Code Dev Container configuration should be committed to this repository. Developers can obtain the latest environment updates by pulling the latest changes from Git.

---

# Version

Current Version: **1.0.0**

---

© Thulija Technology
