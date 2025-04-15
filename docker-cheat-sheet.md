# Docker Cheat Sheet

## Containers

- **`run`** - Start a container from an image.

    ```Docker
    docker run IMAGE
    ```

- **`ps`** - List containers.

    ```Docker
    # Show only running containers
    docker ps
    # Show all containers (including stopped ones)
    docker ps -a
    ```

- **`stop`** - Stop a running container.

    ```Docker
    docker stop CONTAINER_NAME
    ```

- **`rm`** - Remove a container.

    ```Docker
    docker rm CONTAINER_NAME
    ```

## Images

- **`images`** - List all images.

    ```Docker
    docker images
    ```

- **`rmi`** - Remove an image.

    ```Docker
    docker rmi IMAGE
    ```

- **`pull`** - Download an image from a registry (without running it).

    ```Docker
    docker pull IMAGE
    ```

## Working with Containers

- **`exec`** - Execute a command inside a running container.

    ```Docker
    docker exec CONTAINER_NAME COMMAND
    # Example:
    docker exec CONTAINER_NAME cat /etc/hosts
    ```

- **`logs`** - Show logs from a container.

    ```Docker
    docker logs CONTAINER_NAME
    ```

- **`inspect`** - Inspect detailed information about a container or image.

    ```Docker
    docker inspect CONTAINER_NAME
    ```

## Environment Variables

- **Set environment variables when running a container:**

    ```Docker
    docker run -e ENV_VARIABLE=value IMAGE
    ```

## Running Containers in Background or Foreground

- **Run in detached mode (background):**

    ```Docker
    docker run -d IMAGE
    ```

- **Reattach to a running container:**

    ```Docker
    docker attach CONTAINER_NAME
    # or
    docker attach CONTAINER_ID
    ```

## Docker Compose

- **`up`** - Start and run all services defined in a `docker-compose.yml` file.

    ```Docker
    docker compose up
    ```

  - Add `-d` to run in detached mode:

      ```Docker
      docker compose up -d
      ```

- **`down`** - Stop and remove all services and networks defined in the `docker-compose.yml` file.

    ```Docker
    docker compose down
    ```

- **`ps`** - List all running services.

    ```Docker
    docker compose ps
    ```

- **`logs`** - View logs for all services.

    ```Docker
    docker compose logs
    ```

  - Add `-f` to follow logs in real-time:

      ```Docker
      docker compose logs -f
      ```

- **`build`** - Build or rebuild services.

    ```Docker
    docker compose build
    ```

- **`restart`** - Restart services.

    ```Docker
    docker compose restart
    ```

- **`exec`** - Execute a command in a running service container.

    ```Docker
    docker compose exec SERVICE_NAME COMMAND
    # Example:
    docker compose exec web ls /app
    ```

- **`config`** - Validate and view the configuration of the `docker-compose.yml` file.

    ```Docker
    docker compose config
    ```

## Notes

- Replace `IMAGE` with the name of the image (e.g., `nginx`, `ubuntu`).
- Replace `CONTAINER_NAME` or `CONTAINER_ID` with the name or ID of the container.
- Replace `SERVICE_NAME` with the name of the service defined in the `docker-compose.yml` file.
- Use `docker ps` or `docker compose ps` to find running containers and their IDs.
