FROM ubuntu:latest
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -y dist-upgrade && \
    DEBIAN_FRONTEND=noninteractive apt-get -yq install net-tools nginx supervisor
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get -y install openjdk-8-jdk wget
RUN mkdir /usr/src/myapp
ENV JAVA_HOME /usr/java/latest
COPY . /usr/src/myapp/
COPY default /etc/nginx/sites-enabled/
WORKDIR /usr/src/myapp/
ADD  supervisord.conf /etc/supervisor/conf.d/supervisord.conf
