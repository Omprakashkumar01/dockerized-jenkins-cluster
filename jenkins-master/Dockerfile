FROM jenkins/jenkins:lts

USER root

RUN apt-get update && \
    apt-get install -y openssh-client ansible && \
    apt-get clean

USER jenkins

