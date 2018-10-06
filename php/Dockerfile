FROM php:7.1.22-fpm-alpine
RUN docker-php-ext-install mysqli

ADD ./php.ini /usr/local/etc/php/conf.d/90-php.ini