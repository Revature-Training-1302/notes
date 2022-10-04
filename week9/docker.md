## Containers
- Container - a mechanism for packaging an app with its dependencies so that it runs in its own isolated sandbox
    - Dependency examples:
        - Installing JDK
        - Installing Maven
        - Node
    - Ensure app can run regardless of host environment
    - Container can't change host environment (And vice versa)
    - Secure
        - Isolation and virtualization
        - Standardized/portable
        - Lightweight
            - shares the OS' kernel
        - Scalable
- Control groups (cgroups)
    - controlling resources for a particular process
        - memory, CPU, stopping/starting
- Namespaces
    - Determine what is visible to a particular process
- Virtualization - provide a virtualized view of some set of resources

## Virtual Machines
- Virtualize the entire OS
- Bulky, compared to containers
- Hypervisor - coordinates between multiple vms and interfaces

## Images
- Template for container
- Container is a runnable instance of an image

## Docker

### Architecture
- Client-Server Architecture

### Docker Daemon
- Long running process that is responsible for managing Docker objects
- Listens for calls to manage containers, images, volumes, etc.
- The "server" of the client-server architecture

### Docker CLI Client
- How we interact with the Docker daemon
- Commands prefaced by "docker"
- Cheatsheet: https://dockerlabs.collabnix.com/docker/cheatsheet/

### Docker Objects
- Managed by Docker daemon
- Container - runnable instance of the image
- Images - template for the container

#### Docker Images
- Images - the template that outline dependencies for a particular container and its primary process
- Blueprint for a container
- docker pull *image name*
- docker push *image name*

#### Docker Containers
- Running instance of a set of processes and dependencies
- Build from a Docker image
- Docker containers run on a Linux system share the host OS
- On Windows, there is an additional layer of virtualization
    - Must have Hyper-V and virtualization enabled
        - WARNING - Back-Up system before installation
- Docker Container States:
    - created
    - restarting
    - running
    - paused
    - exited
    - dead

### DockerFile
- a file on our computer (must have the name "Dockerfile")
- Defines everything needed for an image
    - starting point
    - dependencies
    - commands to run
- Almost always begin with "FROM" indicating a parent/base image
- [Docker File Cheatsheet](https://kapeli.com/cheat_sheets/Dockerfile.docset/Contents/Resources/Documents/index)

### Docker Best Practices
- Minimal configuration, easy to build up and tear down
- Lightweight
    - Build Context - working directory is sent to the daemon when the image is created, so try to keep our working directory light
    - Multi-Staged builds
        - Previous layers are cached, which could save time later
- Decoupling/Single Responsibility
- Dockerfile should be readable, different commands on different lines

### Docker Flow
1. Use docker build or docker pull to acquire an image
2. Docker creates the image by pulling it from a registry or creates the image itself
3. Use docker run to run the image
4. CLI tells the daemon to spin up a container from the image
5. Use CLI commands to manage the running container

### Docker Commands
- docker build anyflags PATH
    - builds a docker image with any flags specified based on the files specified by PATH
    - Find flags here: https://docs.docker.com/engine/reference/commandline/run/

### Docker flags:
- -t give our container a tag name
- -p 80:80 take port 80 from the container and map it to port 80 on our own machine, allowing us to access that port


### Resources
- [Docker Docs](https://docs.docker.com/)
- [Docker Command Cheatsheet](https://dockerlabs.collabnix.com/docker/cheatsheet/)
- [Dockerfile cheatsheet](https://kapeli.com/cheat_sheets/Dockerfile.docset/Contents/Resources/Documents/index)
- [Docker CLI](https://docs.docker.com/engine/reference/commandline/docker/)
- [Docker Playground](https://labs.play-with-docker.com/)
- [Angular Docker](https://wkrzywiec.medium.com/build-and-run-angular-application-in-a-docker-container-b65dbbc50be8)
