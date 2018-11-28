fROM php:7.2-fpm-alpine

WORKDIR "/var/www"

RUN apk add --no-cache --update icu-libs icu icu-dev

RUN docker-php-ext-install intl pdo pdo_mysql mbstring
