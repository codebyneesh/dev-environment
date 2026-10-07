# Dev Environment Setup

## Repository Setup

Initialize the local repository:

    git init

Create the initial commit:

    git add .
    git commit -m "Initialize reproducible macOS development environment"

Create the GitHub repository and connect the local repository:

    gh repo create dev-environment --private --source=. --remote=origin --push

Verify the remote:

    git remote -v

    
## Container Runtime

### Initial State

The Docker CLI was already installed:

    docker --version

However, having the Docker CLI does not mean a Docker daemon is running.

I verified this with:

    docker info

The client information was available, but the server returned:

    failed to connect to the docker API at unix:///var/run/docker.sock

### What this means

Docker uses a client/server architecture.

- Docker CLI = client that sends Docker commands
- Docker daemon = service that actually manages containers, images, networks, etc.

On macOS, containers cannot run directly using the macOS kernel because
containers depend on Linux kernel features. A Linux environment is needed.

### My Setup

I chose Colima as the local container runtime instead of Docker Desktop.

Install:

    brew install colima

Start the runtime:

    colima start

Verify Docker can communicate with the runtime:

    docker info

Test by running a container:

    docker run --rm hello-world

### Troubleshooting

If Docker commands work but `docker info` cannot connect to the server,
check whether Colima is running:

    colima status

Start it if necessary:

    colima start

Stop it with:

    colima stop
