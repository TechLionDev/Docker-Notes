# Docker Basics

Docker is a powerful tool for recreating a development environment on the fly for an application.

- **CLI Tool**: `docker` is your command-line interface tool.

## Commands To Know

- **List Running Containers**: `docker ps`

## The Dockerfile

A Dockerfile is a script that contains instructions for building a Docker image.

- **FROM**: Specifies the base image (e.g., Node.js base image).
- **WORKDIR**: Equivalent to the `cd` command. Sets the working directory.
  - `/app` is the root directory.
- **COPY**: Copies a file with two parameters: file to copy and target location.
- **RUN**: Executes a command, similar to opening a terminal and running a command.
- **.dockerignore**: Similar to .gitignore, it allows using `COPY . .` without copying certain files (e.g., `node_modules`).
- **ENV**: Sets environment variables.
- **EXPOSE**: Potentially allows a port to be viewed.
- **CMD**: Runs the final start/serve script.
  - Only allowed once in Dockerfile.
  - Uses *Exec Form* (e.g., `[ "npm", "start" ]`).

## Making Dockerfile Useful

Use the following commands to build and run Docker images:

- **Build Image**: `docker build`
  - **Flags**:
    - `-t`: Tag. Gives the image a name (format: `username/imageName:VersionNum`).
  - Path to Dockerfile should be added after all flags.

- **Run Container**: `docker run`
  - Use either container ID or Tag name (from the `-t` flag) to spin up a container.
  - **Flags**:
    - `-p`: Port Forwarding. Forwards ports from the container to the host (`DESIRED_PORT_ON_HOST:EXPOSED_PORT_FROM_DOCKERFILE`).

Remember, all flags come before the container ID or Tag Name.
