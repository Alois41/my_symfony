FROM php:7-fpm

RUN apt-get update \
 && apt-get install -y bzip2 git vim wget \
        libxslt1.1 libxslt1-dev \
        libicu-dev \
        libmcrypt-dev \
        libfreetype6-dev libjpeg62-turbo-dev \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN docker-php-source extract \
 && docker-php-ext-install ext-install gd \
 && docker-php-ext-install intl \
 && docker-php-ext-install opcache \
 && docker-php-ext-install pdo_mysql mysqli \
 && docker-php-ext-install xsl \
 && docker-php-ext-install zip \
 && pecl install redis && docker-php-ext-enable redis \
 && docker-php-source delete

EXPOSE 9000
