+++
title = "Orchestrating a dockerized Robot Framework test through Kubernetes"
description = "Automation setup"
slug = "orchestrating-dockerized-robotframework-test-through-kubernetes"
tags = [
    "docker",
    "jenkins",
    "robotframework",
    "architecture",
    "design",
    "orchestration"
]
categories = [
    "Projects",
]
+++

#### Tools Stack

_To know more about these, please click the links below._

* [Robot Framework](https://robotframework.org/)
* [Jenkins](https://www.jenkins.io/)
* [Docker](https://www.docker.com/)
* [Kubernetes](https://kubernetes.io/)
* [Kibana](https://www.elastic.co/kibana)
* [Grafana](https://grafana.com/)
* [Slack](https://slack.com/intl/en-ph/)

#### Design Diagrams

**Pipeline**

![alt text](/img/ver1.1.jpg "Pipeline")

**Dockerized Robot Framework Test**

* Setting Environment variables
* Maintanable Dockerfile
* Deployed as a K8s Job

![alt text](/img/ver2.0.jpg "Robot Container")

#### How it works / Ideas 

* QE/DevOps push the code changes to the repository including config service
* Dockerized robotframework - packages and libraries needed
* Jenkins Pipeline - Start to End (Refer to the diagram)
* Maintanable Dockerfile of Robot Framework 
* Execution of dockerized robotframework in k8s as a POD
* Parallel execution in different environment (DEV, QA, STG and PROD) tru config service
* setting of  inject variable to which environment will be running of dockerized scripts

#### Resources

[Robot Framework Repository](#)  
[Slack Channnel](#)


