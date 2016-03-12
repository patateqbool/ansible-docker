FROM debian:latest
MAINTAINER from patate <joffrey.guilbon@inpt.fr>

ADD keys/id_rsa.pub /root/.ssh/authorized_keys
RUN apt-get -y update \
    && apt-get -y install openssh-server \
    && apt-get -y install python \
    && apt-get clean all \
    && service ssh start \
    && service ssh stop

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
