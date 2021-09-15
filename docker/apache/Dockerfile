FROM php:7.4-apache

# PHP extensions
RUN apt-get update && apt-get install -y \
        curl \
        libpng-dev \
        libzip-dev \
        zlib1g-dev \
        libonig-dev \
        libwebp-dev \
        libxml2-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
    && pecl install xdebug \
    && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip opcache simplexml xml \
    && docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ --with-webp=/usr/include/ \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install -j$(nproc) gd

# Apache modules
RUN a2enmod rewrite

#composer
RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

ENV APACHE_RUN_USER vladb
ENV APACHE_RUN_GROUP vladb
RUN adduser --uid 1000 --gecos 'My Apache User' --disabled-password vladb