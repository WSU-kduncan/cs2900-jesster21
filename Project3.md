1.	Investigate available mounts
    a. Docker:
        i.	Mount types available are bind mounts and volumes.
        ii.	Volumes: store data but do not control where the data is stored. Bind mounts: control the exact mountpoint on the host and while you can use it to persist data, its often used to provide additional data into containers
    b.	Singularity:
        i.	The mount type is bind mount.
            ii.	The bind mount is a shared folder on the system. Outside containers cannot access the data inside the host container.
2.	Investigate building images for the container engine
    a.	Docker:
        i.	Command: docker image build
        ii.	Write a build file: 
            1.	FROM debian:latest
            2.	RUN apt-get update
            3.	COPY some_file
    b.	Singularity:
        i.	Command: singularity create
        ii.	Write a build file: 
            1.	FROM debian:latest
            2.	RUN apt-get update
            3.	COPY some_file

I want to apogize in advance. I do not know why it looks terrible on github when I pushed it through. It looks fine on visual studio code!