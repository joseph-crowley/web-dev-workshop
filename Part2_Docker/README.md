# Docker-Based Django Development Environment

In this section, we will set up a Docker-based development environment for our Django application. This setup allows us to run a Django project inside a Docker container, which provides an isolated and consistent development environment for all participants.

## Files Description

- `Dockerfile`: This is a script used by Docker to create an image of our development environment. It includes all the instructions on how to set up the image, including installing Python, Django, and other necessary packages.

- `docker-compose.yml`: A YAML file used by Docker Compose to define and run multi-container Docker applications. For our purposes, it simplifies the process of building and running our Dockerized Django environment.

## Setting Up the Environment

Before we begin, ensure you have Docker and Docker Compose installed on your system. You can download them from the [official Docker website](https://docs.docker.com/get-docker/).

### Building the Docker Image

1. Open a terminal or command prompt.
2. Navigate to the directory containing the `docker-compose.yml` file.
3. Run the following command to build the Docker image:

    ```bash
    docker-compose build
    ```

This command tells Docker Compose to look for the `Dockerfile` in the directory specified and build an image according to the instructions found in that `Dockerfile`.

### Running the Container

Once the image is built, you can start the container with the following command:

```bash
docker-compose up
```

This command starts the Django development server inside the container, making it accessible through your web browser at `http://localhost:8000`.

## What to Expect

When you run `docker-compose up`, Docker will:

- Start a container based on the image built from the `Dockerfile`.
- Mount the current directory to `/usr/src/app` inside the container, so changes made locally will reflect inside the container.
- Bind your local port 8000 to the container's port 8000, so you can access the Django app in your web browser.

You should see output in your terminal indicating that the server is running, and you will be able to open your web browser to `http://localhost:8000` to see the Django welcome page.

## Interacting with the Django Container

To interact with the Django server or to run management commands, you can open another terminal and run:

```bash
docker-compose exec web python manage.py <command>
```

Replace `<command>` with Django management commands such as `startproject`, `startapp`, `migrate`, etc.

## Next Steps

Now that your development environment is set up, you're ready to start working on the Django project. In the next part of the workshop, we will use this environment to create a new Django project and app.