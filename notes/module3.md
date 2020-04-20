# Module 3 - Advanced docker topics

Docker Container Lifecycle

Docker Private Registry

Multistage Dockerfiles

Data Management with Docker

Docker Compose

Limiting Memory and CPU for Docker containers

Docker Networking



When you stop a docker container, everything inside it is discarded. In case you want to persist data you will need have some data management. Sharing data etc. 



Docker registry is somewhere to store a number of docker images. Scalable

cat ~\\.docker\\config.json

Use docker login to login to a registry

Then docker push to push an image. 

Convention is to start with the container registy e.g. containerregistry.containername:version

Use docker tag to rename. Doesn't create a new image but links to the original one. 

### Multi-stage dockerfile

Leverage the fact that development will require more resources in the docker container than at runtime. 

Therefore development container can be larger than the small runtime container. 

Can have multiple FROMS which enable containers to be as small as possible. 



### Angular CI Pipeline

Run npm install

run npm build prod (creates production artifacts)

Publish production artifacts