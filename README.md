Reference from Medium page https://medium.com/greedygame-engineering/so-you-want-to-dockerize-your-react-app-64fbbb74c217

Build Docker - `docker build . -t react-docker`

Run Docker - `docker run -p 8000:80 react-docker`

export Docker to Tar file - `docker save react-docker > react-docker-example.tar`

import from tar - `docker load < react-docker-example.tar` then use run docker command with the name allocated to the docker image as `docker_image:latest` (here as `react-docker:latest`)