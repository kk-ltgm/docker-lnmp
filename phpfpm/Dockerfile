
FROM php:5.6-fpm

MAINTAINER kangkai<kangkai@haodai.net>

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install gettext mysqli opcache pdo_mysql sockets

# Install PECL extensions
RUN apt-get install -y \
#    && pecl install xdebug && docker-php-ext-enable xdebug \
    && pecl install redis && docker-php-ext-enable redis \
#    && pecl install xhprof && docker-php-ext-enable xhprof \
    && docker-php-source delete \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* \
    && echo 'PHP 5.6 installed.'


WORKDIR "/var/www"

VOLUME ["/var/www"]