# Welcome to the official Hue (http://gethue.com) developer Dockerfile
#FROM centos:centos7
#
#MAINTAINER The Hue Team "http://git.intra.weibo.com/recommend/hue.git"
#
#RUN yum -y update
#
## Install dependency
#RUN yum -y install \
#git \
#ant \
#asciidoc \
#cyrus-sasl-devel \
#cyrus-sasl-gssapi \
#cyrus-sasl-plain \
#gcc \
#gcc-c++ \
#krb5-devel \
#libffi-devel \
#libtidy \
#libxml2-devel \
#libxslt-devel \
#make \
#maven \
#mysql \
#mysql-devel \
#openldap-devel \
#python-devel \
#sqlite-devel \
#openssl-devel \
#gmp-devel
#
## Install hue
#RUN git clone http://git.intra.weibo.com/recommend/hue.git
#WORKDIR hue
#
## make hue
#RUN make apps
#EXPOSE 8888
#VOLUME /data1/hue/desktop
#CMD ["build/env/bin/hue", "runserver_plus", "0.0.0.0:8888"]
## Start hue  http://0.0.0.0:8888
## If you use boot2docker, you should change ip.
## Please check your `$ boot2docker ip`.








FROM ubuntu:trusty
MAINTAINER The Hue Team "https://github.com/cloudera/hue"

RUN apt-get update -y

RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update -y

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java8-installer

RUN apt-get update -y
RUN apt-get install --fix-missing -q -y \
  git \
  ant \
  gcc \
  g++ \
  libkrb5-dev \
  libmysqlclient-dev \
  libssl-dev \
  libsasl2-dev \
  libsasl2-modules-gssapi-mit \
  libsqlite3-dev \
  libtidy-0.99-0 \
  libxml2-dev \
  libxslt-dev \
  libffi-dev \
  make \
  maven \
  libldap2-dev \
  python-dev \
  python-setuptools \
  libgmp3-dev \
  libz-dev

RUN ["git", "clone", "https://github.com/sunmeng007/hue.git"]
WORKDIR hue
RUN ["git", "pull"]
RUN ["git", "checkout", "sunmeng3-3.12.0"]
RUN ["git", "pull", "origin", "sunmeng3-3.12.0"]
RUN make apps
EXPOSE 8888
VOLUME /hue/desktop/
CMD ["build/env/bin/hue", "runserver_plus", "0.0.0.0:8888"]
