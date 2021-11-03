1. Investigate available mounts
    a. Docker:
        i. Moun ttypes available are bind mounts and volumes
        ii. Volumes: store data but do not control where the data is stored. Bind mounts: control the exact mountpoint on the host and while you can use it to persist data, it is often used to provide additional data into containers
    b. Sinularity:
        i. The mount type is bind mount.
        ii. The bind mount is a shared folder on the system. Outside containers cannot access the data inside the host container.

2. Investigate building images for the container engine
    a. Docker:
        i. Command: docker image build
        ii. Write a build file:
            FROM debian:latest
            RUN apt-get update
            COPY some_file
    b. Singularity:
        i. Command: sinularity create
        ii. Write a build file:
            FROM debian:latest
            RUN apt-get update
            COPY some_file