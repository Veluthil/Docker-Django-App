# Django Docker Compose Template

This repository serves as a template for setting up a Django project with Docker and Docker Compose. It includes configurations for running a PostgreSQL database container, a Redis cache container, and a Celery worker container.

## Prerequisites

Make sure you have the following software installed on your machine:

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/Veluthil/Docker-Django-App.git
   ```

2. Change into the project directory.

3. Build and start the Docker containers:

   ```bash
   docker-compose up --build
   ```

4. Open your web browser and visit `http://localhost:8000` to access the Django application.

## Project Structure

The project structure follows the standard Django layout, with some additional Docker-specific files and directories. Here's a brief overview:

- `Dockerfile`: Contains instructions for building the Docker image for the Django application.
- `docker-compose.yml`: Defines the services and configurations for running the Docker containers.
- `requirements.txt`: Lists the Python dependencies required by the Django application.
- `data/`: The databse directory.
- `core/`: A sample Django app directory. You can create additional apps following this structure.

## Additional Notes

- By default, the Django development server runs on port 8000. If you need to use a different port, update the `docker-compose.yml` file accordingly.
- The PostgreSQL database data is stored in the `data/` directory in the project root. This directory is mounted as a volume in the PostgreSQL container, allowing the data to persist across container restarts.
- The Celery worker is automatically started when the Docker containers are launched. You can add tasks in your Django app and configure Celery to process them asynchronously.
