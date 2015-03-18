FROM ubuntu

MAINTAINER Innovint, Inc. "http://innovint.us"

RUN echo "deb http://archive.ubuntu.com/ubuntu trusty main universe" > /etc/apt/sources.list

RUN apt-get install -y software-properties-common python-software-properties
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y ruby

RUN wget https://github.com/rashidkpc/Kibana/archive/v0.2.0.tar.gz && tar -zxvf v0.2.0.tar.gz && mv 0.2.0 /kibana

