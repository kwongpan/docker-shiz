FROM dockerfile/nodejs

MAINTAINER Andrew Headrick "github.com/bigtoast"

RUN \
  apt-get update && \
  apt-get install -y zsh && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_US.UTF-8

ENV LANG en_US.UTF-8

ENV LANGUAGE en_US:en

ENV LC_ALL en_US.UTF-8

#RUN export PHANTOMJS_CDNURL=http://cnpmjs.org/downloads

RUN npm install -g bower grunt-cli yo phantomjs
# protractor

# maybe later.. gotta see how selenium dockerfiles work
#RUN webdriver-manager update

RUN curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | bash

CMD ["zsh"]
