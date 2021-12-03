1. Investigate container networking:
    a. Docker:
        i. Network nodes that are supported are host, none, and bridge.
            1. Host shares network stack with the host machine
            2. None fully isolates namespaces and has no routes
            3. Bridge makes namespaces not shared and routes traffic to the host and allows port forwarding.
        ii. The networking mode that is set by default is bridge.
        iii. How to run the container and bind a host port to the container port is "docker run -dit -p HOST_PORT:CONTAINER_PORT"

    b. Podman:
        i. Network nodes that are supported are bridge, none, container:<id>, host, network-id, ns:<path>, private, and slirp4nethns.
            1. Bridge creates a network stack on the default bridge network.
            2. None allows no networking
            3. Container:<id> uses the same network as another container id
            4. Host uses the host's network stack
            5. Network-id uses a user-defined network
            6. Ns:<path> joins a network namespace for the container
            7. Private creates a new network namespace for the container
            8. Slip4nethns creates a user network stack with slirp4nethns, which is the default option for rootless containers
        ii. The networking mode that is set by default is bridge.
        iii. How to run the container and bind a host port to the container port is "podman run -dt -p HOST_PORT:CONTAINER_PORT"

2. Investigate vulnerability scanners:
    a. Hadolint- The linter parses the Dockerfile into an AST and performs rules on top of the AST. It stands on the shoulders of ShellCheck to lint the bash code inside RUN instructions.

    b. Aqua Trivy- Scans container images, filesystm, and git repositories. You should only specify an image name, a path to config files, or an artifact name. 
    
    It detects vulnerabilities of OS packages (Alpine, RHEL, CentOS, etc.) and language-specific packages (Bundler, Composer, npm, yarn, etc.). It also scans infrastructure as code such as Terraform and Kubernetes. 