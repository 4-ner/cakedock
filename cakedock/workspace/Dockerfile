FROM php:fpm-alpine

USER root

RUN echo http://dl-2.alpinelinux.org/alpine/v3.6/community/ >> /etc/apk/repositories
RUN apk update \
    && apk upgrade \
    && apk add --no-cache bash \
    && apk --no-cache add shadow

ARG PUID=1000
ENV PUID ${PUID}
ARG PGID=1000
ENV PGID ${PGID}

RUN groupadd -g ${PGID} cakedock && \
    useradd -u ${PUID} -g cakedock -m cakedock && \
    usermod -p "*" cakedock

RUN apk add --no-cache --update icu-libs icu icu-dev && rm /var/cache/apk/*
RUN docker-php-ext-install intl

WORKDIR "/var/www"

RUN curl -s http://getcomposer.org/installer | php && \
    echo "export PATH=${PATH}:/var/www/vendor/bin" >> ~/.bashrc && \
    mv composer.phar /usr/local/bin/composer

RUN . ~/.bashrc
