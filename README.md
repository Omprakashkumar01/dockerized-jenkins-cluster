# **Jenkins Master-Agent Setup using Docker and SSH Authentication**

## **Overview**

This project sets up a Jenkins master-agent architecture using Docker containers. The Jenkins master connects to the Jenkins agent using SSH to delegate job executions. The setup includes building Docker images from scratch, configuring SSH authentication, and resolving common Jenkins connection issues.

---

## **Project Structure**

project-root/  
├── docker-compose.yml  
├── jenkins-master/  
│   └── Dockerfile  
├── jenkins-agent/  
│   └── Dockerfile

---



## Common Errors and Fixes

### ❌ Authentication failed (private key rejected)

* Make sure the public key is correctly copied to the agent's `authorized_keys`.

* Ensure correct permissions: `chmod 600 authorized_keys` and `chmod 700 .ssh`

### ❌ Unsupported Java version

* Update agent Dockerfile to install OpenJDK 17 (compatible with remoting.jar):

apt-get install \-y openjdk-17-jdk

### ❌ Cannot access `/var/jenkins_home` from host

* Use `docker exec -it jenkins-master bash` instead.

---

## **Final Result**

A fully working Jenkins master-agent setup over SSH with Docker, allowing Jenkins to distribute builds securely using key-based SSH authentication.
