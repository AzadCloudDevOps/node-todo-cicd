[![LinkedIn](https://img.shields.io/badge/in-linkedin-blue.svg)](https://www.linkedin.com/in/akash-zade/)

 <h2 align="center">Nodejs-Todolist-App</h2>

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

#for only current server
npm install
node app.js
```

### Installation

* Install [Docker](https://docs.docker.com/engine/install/ubuntu/)
* Check if docker version using **docker --version**
* Install Java Development Kit (JDK)
* Set path for the Environmental variable for JDK
* Download and Install [Jenkins](https://pkg.origin.jenkins.io/debian-stable/)
* Check the Jenkins version using **jenkins --version**
* Check if jenkins service is running using **systemctl status jenkins**

### Fork the repository
```bash
git fork https://github.com/AzadCloudDevOps/node-todo-cicd.git
```

### Set authentication ssh-keys in server
```bash
ssh-keygen
cd .ssh
cat id_rsa.pub
cat id_rsa
```

### Set public connection of Server with GitHub via SSH
* Open GitHub personal account setting
* Select SSH and GPG keys
* Add new ssh-key
* Set title, Key(paste here id_rsa.pub)

### Webhook

Webhook in jenkins triggers pipeline automatically when any changes are done in github repo like commit and push.

* Copy jenkins URL 
* Go to repo settings in github
* Select Add webhook and paste URL
* Append url with /github-webhook/

### Continuous Deployment
#### Using Dockerfile
* Login into Jenkins with credentials say username and password
* Create a new item of freestyle project
* Set description for your project.
* Add GitHub repo Url in GitHub project.
* Add Git in Source code management.
* Set credentials with SSH username and private key(paste here id_rsa)
* Add Build triggers say **GitHub hook trigger for GITScm** for webhook automation.
* Add Build Steps for command of docker
use
```bash
docker build . -t <image_tag>
docker run -d --name <container_name> -p <ext_port>:<int_port> <image_tag>
```
* Save the project.

#### Using Docker-compose.yaml file
* Uncheck the GitHub trigger
* Modify the docker-compose.yaml file in forked repository or create new one.
* Again check GitHub trigger.
* Add Build step
Use
```bash
docker compose down
docker compose up -d --build
```
* Save the project.
* Install **GitHub integration** plugin via manage plugin.
* Test the application via changing the GitHub repo code.





