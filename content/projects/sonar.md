+++
title = "Dockerized Sonarqube, Sonar Scanner through Jenkins"
description = "Scan code without hassle"
slug = "dockerized-sonarqube-using-jenkins-pipeline"
tags = [
    "docker",
    "cli",
    "client",
    "jenkins",
    "sonar"
]
categories = [
    "Projects",
]
+++
### Overview

SonarQube is an open-source automatic code review tool to detect bugs, vulnerabilities, and code smells in your code. It provides us with a beautiful dashboard with the functionality of in-detail scanning data where we can analyze our code quality and improve it.

### Installation

Step 1: Clone the repository to your local machine.

```sh
$ git clone https://github.com/edsherwin/docker-sonar-jenkins.git   
```

Step 2: Instantiate then Jenkins using the _Dockerfile.jenkins_

```sh
$ docker build -t jenkins-docker -f Dockerfile.jenkins .
$ docker run -d -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock --name jenkins-docker jenkins-docker:latest
```


Step 3: Check if the Jenkins is running. Also, check if it's mounted to the host machine's Docker socket in the container. This will allow your container to use the host machine's Docker daemon to run containers and build images.

```sh
$ docker ps -a
$ docker exec -it jenkins-docker bash
$ docker --version or docker ps
```

Step 4: Instantiate the Sonarqube

```sh
$ docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

Step 5. Create a Project in Sonarqube

Make sure to change the below config in _sonar-runner.properties_

```sh
#The IP Address of your docker container
sonar.host.url=http://172.17.0.3:9000
sonar.projectKey=ABCProject
sonar.projectName=ABCProject
sonar.projectVersion=1
sonar.login=a4b182a683d8f20f80babc2f14c96e0c22a49fd7
```


Step6. Create a Build Pipeline job in Jenkins





