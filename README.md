# Demo Projects 

## Setup
### Install Jenkins on DigitalOcean 
1. Create an Ubuntu Server on DigitalOcean
2. Make sure to configure ssh and ssh into your server
3. Update package manager and install docker 
   ```
   apt update
   apt install docker.io 
   ```
5. Set up and run Jenkins as a Docker container (see [docker hub](https://hub.docker.com/_/jenkins) on how to pull and run a jenkins Docker Image)
     
   ```
   docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins/jenkins:lts
   ```
   
8. Initialize Jenkins 
### 1. Create CI Pipeline with Jenkinsfile (Freestyle, Pipeline, Multibranch Pipeline)
- Project Description: tbc 
- Technologies used: Jenkins, Docker, Linux, Git, Java, Maven
