FROM dockerfile/java:oracle-java8

MAINTAINER Andrew Headrick "github.com/bigtoast"

RUN apt-get update && apt-get install -y zsh ruby ruby-dev ruby-bundler mongodb-clients && rm -rf /var/lib/apt/lists/*

RUN locale-gen en_US.UTF-8

ENV LANG en_US.UTF-8

ENV LANGUAGE en_US:en

ENV LC_ALL en_US.UTF-8

# install scala
RUN wget http://downloads.typesafe.com/scala/2.11.6/scala-2.11.6.tgz && \
    tar xzf scala-2.11.6.tgz -C /usr/share/ && \
    rm scala-2.11.6.tgz && \
    ln -s /usr/share/scala-2.11.6 /usr/share/scala

# symlink scala binary to /usr/bin
RUN for i in scala scalc fsc scaladoc scalap; do ln -s /usr/share/scala/bin/${i} /usr/bin/${i}; done

ENV SCALA_HOME /usr/share/scala

RUN wget https://raw.githubusercontent.com/paulp/sbt-extras/master/sbt -O /usr/bin/sbt \
  && chmod 0755 /usr/bin/sbt

RUN curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | bash

RUN gpg --keyserver pool.sks-keyservers.net --recv-keys 7937DFD2AB06298B2293C3187D33FF9D0246406D 114F43EE0176B71C7BC219DD50A3051F888C628D

ENV NODE_VERSION 0.10.37

ENV NPM_VERSION 2.7.1

RUN curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc" \
    && gpg --verify SHASUMS256.txt.asc \
    && grep " node-v$NODE_VERSION-linux-x64.tar.gz\$" SHASUMS256.txt.asc | sha256sum -c - \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc \
    && npm install -g npm@"$NPM_VERSION" \
    && npm cache clear

RUN gem install jekyll

VOLUME ["/source"]

RUN cd /source

CMD ["zsh"]
