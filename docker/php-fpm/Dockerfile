FROM php:7-fpm

RUN apt-get update \
 && apt-get install -y bzip2 git vim wget \
        libxslt1.1 libxslt1-dev \
        libicu-dev libzip-dev\
        libmcrypt-dev \
        libfreetype6-dev libjpeg62-turbo-dev \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install gd \
 && docker-php-ext-install intl \
 && docker-php-ext-install opcache \
 && docker-php-ext-install pdo_mysql mysqli \
 && docker-php-ext-install xsl \
 && docker-php-ext-install zip \
 && pecl install redis && docker-php-ext-enable redis

RUN chown -R www-data:www-data /var/www

EXPOSE 9000
