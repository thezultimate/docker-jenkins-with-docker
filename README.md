# Jenkins in Docker with Docker

This is a simple template for running Jenkins inside a Docker container with Docker installed.

It can be run, e.g., by running the following steps:

1. Create a home directory for Jenkins and change its ownership:

        sudo mkdir -p ~/jenkins
        sudo chown -R 1000:1000 ~/jenkins

2. Build the docker image from the `Dockerfile`:

        sudo docker build -t user/jenkins-with-docker .

3. Run the created docker image: 

        sudo docker run -p 8080:8080 -p 50000:50000 -v ~/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock user/jenkins-with-docker