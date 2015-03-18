# bigtoast/java8

FROM ubuntu

MAINTAINER Andrew Headrick "github.com/bigtoast"

# make ubuntu current
RUN apt-get update && apt-get -y upgrade && apt-get -y install wget unzip && apt-get clean
#RUN apt-get -y install wget && apt-get clean

RUN wget -q --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u40-b26/server-jre-8u40-linux-x64.tar.gz

RUN mkdir -p /usr/lib/jvm && tar -zxvf server-jre-8u5-linux-x64.tar.gz -C /usr/lib/jvm && rm server-jre-8u40-linux-x64.tar.gz && ln -s /usr/lib/jvm/jdk1.8.0_40/bin/java /usr/bin/java

ENV JAVA_HOME /usr/lib/jvm/jdk1.8.0_40/
