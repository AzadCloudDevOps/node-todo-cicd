[![LinkedIn](https://img.shields.io/badge/in-linkedin-magenta.svg)](https://www.linkedin.com/in/akash-zade/)

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a> <img src="https://www.vectorlogo.zone/logos/nodejs/nodejs-icon.svg" alt="Logo" width="80" height="80"> </a>
 <h2 align="center">Nodejs-Todo-App</h2>
  <p align="center">
    An awesome project to understand automation of nodejs application using webhook integration!
    <br />
    <br />
    <a href="https://github.com/AzadCloudDevOps">Report Bug</a>
    ·
    <a href="https://github.com/AzadCloudDevOps">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Fork the repository](#fork-the-repository)
* [SSH server connection with GitHub](#ssh-server-connection-with-github)
* [Webhook](#webhook)
* [Continuous Deployment](#continuous-deployment)
* [Usage](#usage)

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these steps.

### Prerequisites

* java
```bash
sudo apt install openjdk-11-jre
java --version
```
* nodejs
```bash
sudo apt install nodejs
sudo apt install npm

#only for current system
sudo npm install
node app.js
```

### Installation

* Install [Docker](https://docs.docker.com/engine/install/ubuntu/)
* Check docker version using **docker --version**
* Install Java Development Kit (JDK)
* Set path for the Environmental variable for JDK
* Download and Install [Jenkins](https://pkg.origin.jenkins.io/debian-stable/)
* Check the Jenkins version using **jenkins --version**
* Check if jenkins service is running using **systemctl status jenkins**

### Fork the repository
```bash
git fork <github_repo_url>
```

###Authorized ssh-keys in server
```bash
ssh-keygen
cd .ssh
ls
```

### SSH server connection with GitHub
* Open GitHub personal account setting
* Select SSH and GPG keys
* Add new ssh-key

### Webhook

Webhook in jenkins triggers pipeline automatically when any changes are done in github repo like commit and push.

* Copy jenkins URL 
* Go to repo settings in github
* Select Add webhook and paste URL
* Append url with /github-webhook/

### Continuous Deployment
#### Using Dockerfile
* Login into Jenkins with credentials say username and password
* Click on new item of freestyle project
* Set description for the project.
* Add GitHub repository Url in GitHub project.
* Add Git in Source code management.
* Set credentials with SSH username and private key.
* Add Build triggers say **GitHub hook trigger for GITScm** for webhook automation.
* Add Build Steps
 ```bash
 docker build . -t <image_tag>
 docker run -d --name <container_name> -p <ext_port>:<int_port> <image_tag>
 ```
* Save the project.
* Install **GitHub integration** plugin via manage plugin.
* Test the application via changing the GitHub repo code.

#### Using Docker-compose.yaml file
* Uncheck the GitHub trigger
* Modify the docker-compose.yaml file in forked repository or create new one.
* Again check GitHub trigger.
* Add Build steps
 ```bash
 docker compose down
 docker compose up -d --build
 ```
* Save the project.
* Install **GitHub integration** plugin via manage plugin.
* Test the application via changing the GitHub repo code.

<!-- USAGE EXAMPLES -->
## Usage

_For better understanding, please refer the [Article](https://akash-zade.hashnode.dev/complete-jenkins-cicd-project)_
