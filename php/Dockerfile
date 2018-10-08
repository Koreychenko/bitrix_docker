FROM php:7.1.22-fpm-alpine
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install mbstring
RUN apk add --no-cache freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev
RUN docker-php-ext-install gd

ADD ./php.ini /usr/local/etc/php/conf.d/90-php.ini