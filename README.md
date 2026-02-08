# Orchestra

The central hub for managing and deploying the **[a-partala](https://github.com/a-partala)** microservices ecosystem.

## Overview
Orchestra is a coordination repository that uses **Git Submodules** to unify independent services. It provides a consistent Docker infrastructure, shared networking (service discovery), and centralized environment configuration.

## Quick Start
```bash
# 1. Clone the repository with all sub-modules
git clone --recursive https://github.com/a-partala/orchestra.git

# 2. Move into the project directory
cd orchestra

# 3. Create a workable .env file from the template
cp .env.example .env

# 4. Spin up the entire ecosystem
docker-compose up --build
```

## Services Map

| Service         | Main Port | Debug Port | DB Port | Description                                                                     | Repository                                        |
|:----------------|:----------|:-----------|:--------|:--------------------------------------------------------------------------------|:--------------------------------------------------|
| **User**        | `:8081`   | `:5005`    | `:5433` | **Identity Provider**. Issues JWT, handles Email Verification & User lifecycle. | [Link](https://github.com/a-partala/user-service) |
| **Task**        | `:8082`   | `:5006`    | `:5434` | **Resource Server**. Stateless authorization based on User identity.            | [Link](https://github.com/a-partala/task-service) |
