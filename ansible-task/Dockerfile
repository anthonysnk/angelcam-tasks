FROM ubuntu:22.04

ARG USER=ubuntu

# Add sudo and openssh-server
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install openssh-server python3 sudo -y

# Setup running user on the container with sudo rights and
# password-less ssh login
RUN useradd -m ${USER}
RUN adduser ${USER} sudo
RUN echo "${USER} ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/sudoers

# start ssh with port exposed
USER root
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]