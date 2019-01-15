FROM php:7.1.22-fpm-alpine
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install mbstring
RUN apk add --update --no-cache \
        freetype-dev \
        libjpeg-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-install -j"$(getconf _NPROCESSORS_ONLN)" iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j"$(getconf _NPROCESSORS_ONLN)" gd
    
ADD ./php.ini /usr/local/etc/php/conf.d/90-php.ini