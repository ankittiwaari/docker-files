FROM php:8.2.0-apache
ARG DEBIAN_FRONTEND=noninteractive
RUN docker-php-ext-install mysqli \
&& sync \
&& apt-get update \
&& apt-get install -y postgresql \
&& apt-get install -y libpq-dev \
&& docker-php-ext-install pdo pdo_mysql pdo_pgsql \
&& a2enmod rewrite \
&& apt-get install -y $PHPIZE_DEPS \
&& pecl install xdebug-3.0.0 \
&& docker-php-ext-enable xdebug \
&& apt-get update \
&& apt-get install nano \
&& apt-get install zip unzip \
&& apt-get install -y libzip-dev \
&& docker-php-ext-configure zip \
&& php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
&& php composer-setup.php \
&& mv composer.phar /usr/local/bin/composer \
&& chmod +x /usr/local/bin/composer
WORKDIR /usr/local/etc/php
COPY php.ini php.ini

