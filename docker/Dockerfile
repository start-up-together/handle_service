FROM php:8.1.18-fpm-alpine3.17 AS base

RUN apk add --update --no-cache bash

ADD https://github.com/mlocati/docker-php-extension-installer/releases/download/2.1.15/install-php-extensions /usr/local/bin/

ENV IPE_GD_WITHOUTAVIF=1

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions \
    @composer-2.5.5

ENV PATH=/var/www/html/vendor/bin:$PATH

ENTRYPOINT ["php-fpm"]

