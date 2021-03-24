FROM php:7.4-apache
RUN docker-php-ext-install mysqli
RUN docker-php-ext-enable mysqli
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-enable pdo_mysql
RUN a2enmod rewrite
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug
RUN apt-get update
RUN apt-get install nano
RUN apt-get install zip unzip
RUN apt-get install -y libzip-dev
RUN docker-php-ext-configure zip
WORKDIR /usr/local/etc/php
COPY php.ini php.ini