FROM ubuntu:trusty

MAINTAINER os369510@gmail.com

ENV User=ubuntu
ENV Contact=os369510@gmail.com

LABEL Owner=os369510

USER root

RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y byobu curl git htop man unzip vim wget && \
  apt-get install -y sudo devscripts debhelper dh-modaliases pbuilder && \
  apt-get install -y systemd tree && \
  rm -rf /var/lib/apt/lists/* \
  rm -rf /tmp/* && \
  rm -rf /var/tmp/*

RUN useradd -ms /bin/bash ${User} && echo "${User}:${User}" | chpasswd && adduser ${User} sudo

USER ${User}

CMD ["bash"]
