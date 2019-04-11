FROM bscheshir/php:7.3.3-fpm-alpine-4yii2-xdebug

MAINTAINER taoyu taoyu65@gmail.com

WORKDIR "/application"

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get -y --no-install-recommends install  php7.2-mysql php-redis php-xdebug php7.2-dba php7.2-imap php7.2-intl php7.2-odbc php7.2-phpdbg php7.2-pspell php7.2-soap php-ssh2 php7.2-xsl php-yaml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && apt-get -y install git \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*