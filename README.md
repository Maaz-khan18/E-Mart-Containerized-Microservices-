# E-Mart Containerized Microservices Ecommerce Application

A full-stack e-commerce application designed for a DevOps-oriented environment, using containerized microservices for frontend, backend APIs, database services, and reverse proxy routing. The project demonstrates how multiple application components can be orchestrated with Docker Compose and deployed as independent services.

## Overview

This application includes:

- Angular frontend for the storefront UI
- Node.js REST API for user and shop operations
- Java Spring Boot API for product/book related services
- MongoDB for document-based data storage
- MySQL for relational data storage
- NGINX as a reverse proxy/load balancer entry point
- Dockerized deployment using Docker Compose

## Architecture

The application is divided into the following services:

- Client: Angular web application
- API: Node.js backend service
- WebAPI: Java Spring Boot backend service
- Nginx: HTTP gateway / reverse proxy
- emongo: MongoDB database
- emartdb: MySQL database

## Tech Stack

### Frontend
- Angular 12
- TypeScript
- Bootstrap
- Font Awesome

### Node API
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT-based authentication
- bcrypt.js for password hashing

### Java API
- Java 8
- Spring Boot 2.3
- Spring Data JPA
- MySQL Connector

### Infrastructure / DevOps
- Docker
- Docker Compose
- NGINX
- Vagrant
- Jenkins support files included in project folders

## Project Structure

```text
E-Mart-Containerized-Microservices/
├── client/                  # Angular frontend application
├── javaapi/                 # Spring Boot microservice
├── nodeapi/                 # Express.js REST API
├── nginx/                   # NGINX config
├── docker-compose.yaml      # Container orchestration
├── Vagrantfile              # VM provisioning config
├── .git/                   # Git metadata
└── README.md               # Project documentation
```

## Services and Ports

| Service | Port | Description |
|--------|------|-------------|
| Angular Client | 4200 | Main front-end application |
| Node API | 5000 | Express API |
| Java API | 9000 | Spring Boot API |
| NGINX | 80 | Reverse proxy |
| MongoDB | 27017 | NoSQL database |
| MySQL | 3306 | Relational database |

## Prerequisites

Before running the project, install:

- Docker
- Docker Compose
- Git
- Optional: Vagrant for VM-based dev environment

## Run the Application

From the project root, run:

```bash
docker-compose up --build
```

This will build and start all containers defined in the compose file.

### Access the application

- Frontend: http://localhost:4200
- NGINX entry: http://localhost
- Node API: http://localhost:5000
- Java API: http://localhost:9000

## Stop the Application

```bash
docker-compose down
```

To remove containers and volumes completely:

```bash
docker-compose down -v
```

## Useful Docker Commands

```bash
# View running containers
docker-compose ps

# View logs
docker-compose logs -f

# Restart a service
docker-compose restart api

# Rebuild a specific service
docker-compose build client
```

## Database Configuration

### MongoDB
- Container name: emongo
- Port: 27017
- Database: epoc

### MySQL
- Container name: emartdb
- Port: 3306
- Root password: emartdbpass
- Database: books

## DevOps / CI-CD Notes

This project includes Jenkins configuration files in the frontend and Java backend folders, which makes it suitable for basic CI/CD workflows. The containerized architecture also makes it easier to deploy in DevOps pipelines, staging environments, and orchestration platforms.

The setup emphasizes:

- Service isolation
- Easier environment replication
- Infrastructure as code practices
- Container-based deployment
- Quick local environment bootstrapping

## Features

- User authentication and authorization
- Product and category browsing
- Shopping flow and order management
- Admin-style product management patterns
- Microservices-based application decomposition
- Dockerized environment for easy deployment

## Security Notes

This project is intended for learning and development use. For production deployment, consider:

- Secure environment variables
- Secrets management
- HTTPS termination at the proxy layer
- Database credentials rotation
- Hardened container images
- Proper access control and validation

## Contribution

Contributions are welcome. You can fork the repository, make improvements, and submit a pull request with your changes.

## License

This project is provided for educational and demo purposes. Please check the repository for licensing details or add your preferred project license before using it in production.

## Summary

This repository is a practical example of a containerized microservices e-commerce application built for a DevOps environment. It combines modern web, APIs, databases, and Docker orchestration into a single project that is easy to run and extend.
