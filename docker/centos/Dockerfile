#################################################################
# Dockerfile to build Zimbra Collaboration 8.7.11 container images
# Based on Centos 7
# Created by Bithedz
#################################################################
FROM centos:latest
MAINTAINER Bithedz <bithedz@gmail.com>

#RUN echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

RUN yum -y --setopt=tsflags=nodocs update && yum -y --setopt=tsflags=nodocs  upgrade &&  yum -y --setopt=tsflags=nodocs  install \
  wget \
  perl \
  dialog \
  bind \
  nc \
  openssh-clients \
  openssh-server \
  dnsmasq \
  bind-utils \
  net-tools \
  sudo \
  rsyslog \
  unzip

VOLUME ["/opt/zimbra"]

EXPOSE 22 25 465 587 110 143 993 995 80 443 8080 8443 7071

COPY opt /opt/

COPY etc /etc/

CMD ["/bin/bash", "/opt/start.sh", "-d"]

