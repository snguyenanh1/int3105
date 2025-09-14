FROM ubuntu:24.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y openssh-server sudo tightvncserver xfce4 xfce4-goodies nano dbus-x11
RUN mkdir /var/run/sshd
RUN useradd -m -s /bin/bash user && echo 'user:1234' |chpasswd && usermod -aG sudo user
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config
EXPOSE 22
EXPOSE 5901
CMD ["/usr/sbin/sshd", "-D"]
