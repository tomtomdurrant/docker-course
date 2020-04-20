# Module 1 - Introduction to Containers

### Containers as a development environment: 

VScode as front end, running the backend against a container. All members of team will have all the same set up. 



**Terminology**:

- Host, A machine running the docker daemon to host a collection of containers

- Client, where docker commands are executed

- Image, An ordered collection of filesystems to be used when instancing a container

- Container, a runtime instance of an image

- Registry, a collection of docker images



### Windows based containers vs Linux based Containers

Image vs container -> Image is a recipe for the container. Container is the instance 

Image is a script that describes the container environment. 



Virtual Machine vs Container 

Virtual machine has to have all the OS prerequisites & download a guest OS.

-  VMs have a lot of overhead, unsuited for a CI pipeline.

Containers share the underlying kernel from the host OS. 

- Faster 

**OS that you're running in the container has to match what is on the host.** 

So if you want to run a linux container on a windows 10 machine these linux containers will run on the DockerDesktopVM. 

Because they are using the same kernel, it might be a security concern if one container is compromised. 



#### Docker Registry

Collection of docker images that have been created. Can pull from there. Like dockerhub

Where to store your custom image. 

- Private registry - Azure container registry is an example of this. 



Docker Engine

The program that enables containers to run. 



Docker uses the linux kernel namespaces and control groups to give each container its own separate space. 

When pulling images from a registry, they will pull lots of layers from the registry

When you pull images this will create a lof of dangling images. THese will ahve been the dependency containers created when pulling other containers. 



#### Pulling docker images

Not a good practice to pull latest tag. Can be a bit unstable etc. 



Docker run 

-d - runs in detached mode 

As docker containers are running in an isolated environment you need a way of getting in to it. Port mapping is how this is achieved. 

-p 80:80 - exposes port 80 from host to port 80 on container

left hand is host : right hand is the container

-v - maps files from host to container



### Dockerfile Commands

FROM - base image for subsequent instructions

LABEL - metadata for your container

RUN - executes any command in a new layer and commits the results

WORKDIR - sets the working directory for the docker image

ADD - adds files to the container. Maybe from a remote location. 

COPY - copy file from host to container

CMD - will execute this command every time the image starts

ENTRYPOINT - allows you to configure a container that will run as an executable. Can pass args to it. 

EXPOSE - expose port on host and container

Prefer ENTRYPOINT to CMD when building executable Docker image and you need a command always to be executed. Additionally use CMD if you need to provide extra default arguments that could be overwritten from command line when docker container runs.

Choose CMD if you need to provide a default command and/or arguments that can be overwritten from command line when docker container runs.	



## Creating a dockerfile

Whenworking with angular and serving using ng serve this uses webpack as a dev server. Moving to production will be then risky as there are different environments. 

Developing against docker containers ensures Dev == production environment. 



docker build. If subsequent builds don't change docker uses caching. Enables quick builds



## Naming Convention

For microsoft/aspnet image these items are as follows 

- REPOSITORY-NAME: microsoft 
- IMAGE-NAME: aspnet 
- TAG: latest (by default) 



### Helpful docker commands

docker history <containername>

