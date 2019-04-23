FROM bscheshir/php:7.3.3-fpm-alpine-4yii2-xdebug

MAINTAINER taoyu taoyu65@gmail.com

WORKDIR "/var/www/html/web/swapsy"

ARG DEBIAN_FRONTEND=noninteractive

RUN apk --update add \
        php7-mysqli \
        git \
        curl \
        curl-dev \
        bash \
        bash-completion \
        libzip-dev \
        freetype-dev \
        icu \
        icu-dev \
        libxml2-dev \
        libintl \
        libjpeg-turbo-dev \
        libpng-dev \
        mysql-client \
        nodejs \
        postgresql-dev && \
    docker-php-ext-configure gd \
        --with-gd \
        --with-freetype-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/ \
        --with-png-dir=/usr/include/ && \
    docker-php-ext-configure bcmath && \
    docker-php-ext-configure pgsql --with-pgsql=/usr/local/pgsql && \
    docker-php-ext-install \
        mysqli \
        soap \
        zip \
        curl \
        bcmath \
        exif \
        gd \
        iconv \
        intl \
        mbstring \
        opcache \
        pdo_mysql \
        pdo_pgsql \
        pgsql && \
    apk del \
        icu-dev \
        gcc \
        g++ && \
    apk add --no-cache tzdata && \
    set -ex

# RUN apk --update add \
#     && apt-get -y --no-install-recommends install phpmyadmin php7.3.3-mysql php7.3.3-mysqli php-redis php-xdebug php7.2-dba php7.2-imap php7.2-intl php7.2-odbc php7.2-phpdbg php7.2-pspell php7.2-soap php-ssh2 php7.2-xsl php-yaml \
#     && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# RUN apk --update add \
#     && apt-get -y install git \
#     && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*