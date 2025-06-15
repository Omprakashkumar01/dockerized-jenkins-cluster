FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y openssh-server sudo openjdk-11-jdk ansible && \
    mkdir /var/run/sshd && \
    useradd -m -s /bin/bash jenkins && \
    echo "jenkins:jenkins" | chpasswd && \
    echo "jenkins ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

