FROM php:fpm-alpine

WORKDIR "/var/www/app"

RUN apk add --no-cache --update icu-libs icu icu-dev && rm /var/cache/apk/*

RUN docker-php-ext-install intl pdo pdo_mysql mbstring

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
