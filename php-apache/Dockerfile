FROM php:7.4-apache
RUN docker-php-ext-install mysqli
RUN docker-php-ext-enable mysqli
RUN a2enmod rewrite
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug
WORKDIR /usr/local/etc/php
COPY php.ini php.ini
RUN apt-get update
RUN apt-get install nano