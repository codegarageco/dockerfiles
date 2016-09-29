FROM ubuntu:14.04

MAINTAINER Faizal Zakaria

RUN echo "# Delete locales \n\
path-exclude=/usr/share/locale/* \n\
# Delete man pages \n\
path-exclude=/usr/share/man/* \n\
# Delete docs \n\
path-exclude=/usr/share/doc/* \n\
path-include=/usr/share/doc/*/copyright"\
>> /etc/dpkg/dpkg.cfg.d/01_nodoc && \
  cat /etc/dpkg/dpkg.cfg.d/01_nodoc

ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
  apt-get dist-upgrade -y --no-install-recommends && \
  apt-get install -y --no-install-recommends software-properties-common && \
  add-apt-repository -y ppa:brightbox/ruby-ng && \
  apt-get update && \
  apt-get install -y --no-install-recommends \
  build-essential checkinstall git-core \
  zlib1g-dev libyaml-dev libssl-dev libgdbm-dev libreadline-dev \
  libncurses5-dev libffi-dev libxml2-dev libxslt-dev libcurl4-openssl-dev libicu-dev \
  graphviz libgraphviz-dev \
  libmysqlclient-dev libpq-dev libsqlite3-dev \
  libqt4-dev libqtwebkit-dev imagemagick wget \
  ruby2.3 ruby2.3-dev && \
  locale-gen en_US.UTF-8 && \
  update-locale LANG=en_US.UTF-8 LC_CTYPE=en_US.UTF-8 && \
  gem install --no-ri --no-rdoc bundler && \
  apt-get purge -y python3* rsyslog rsync manpages && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /usr/share/doc/ && \
  rm -rf /usr/share/man/ && \
  rm -rf /usr/share/locale/ && \
  rm -rf /var/log/*
