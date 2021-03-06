#
# Dockerfile to generate Debian 9 server for Aegir
# to host Durpal & CiviCRM sites
#
# Usage:
#   cd supported-os/debian-stretch
#   docker build -t stretch .
#   docker tag stretch:latest wepoca/stretch-php7
#   docker push wepoca/stretch-php7
#
# ----------------------------------
# Base image & packages:
# - https://hub.docker.com/_/debian/
# - PHP 7.0 prepared for Aegir 3.x and CiviCRM
# - Apache
# - mysql client
# - Postfix
# - utils like sudo, nano, git, wget
#
# ----------------------------------
# TODO:
# - proper clean-up to minimize image size
# - install the PECL uploadprogress library
# - adjust PHP settings
#
# ----------------------------------
# Debian specifics:
# - the official debian Docker image has no cron
#
#
FROM debian:9.4-slim
ENV DEBIAN_FRONTEND=noninteractive
#
RUN apt-get update -qq && apt-get install -y -qq \
  apache2 \
  libapache2-mod-php7.0 \
  php7.0-gd \
  php7.0-curl \
  php7.0-xml \
  php7.0-mbstring \
  php7.0-mysql \
  php7.0-mcrypt \
  postfix \
  cron \
  nano \
  sudo \
  rsync \
  git \
  unzip \
  wget  \
  curl \
  nano \
  default-mysql-client \
  && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/apt/archives && \
  rm -rf /usr/share/doc/ && \
  rm -rf /usr/share/man/ && \
  rm -rf /usr/share/locale/

CMD bash
