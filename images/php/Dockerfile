FROM php:7.4-fpm-alpine
LABEL maintainer="kb10uy"

RUN apk add --no-cache zlib-dev libpng-dev jpeg-dev libwebp-dev freetype-dev \
                       postgresql-dev libzip-dev icu-dev bzip2-dev imagemagick-dev imagemagick \
                       gmp-dev autoconf build-base nodejs yarn make \
    && pecl install imagick redis apcu \
    && docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp \
    && docker-php-ext-install gd zip pdo_pgsql bz2 intl bcmath gmp opcache \
    && docker-php-ext-enable imagick redis apcu \
    && apk del build-base autoconf \
    && curl -o /usr/local/bin/composer https://getcomposer.org/composer-stable.phar \
    && chmod 755 /usr/local/bin/composer
