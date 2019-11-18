FROM php:7.3-fpm

RUN set -e
RUN apt-get update
RUN apt-get install -y apt-utils
RUN apt-get install -y build-essential
RUN apt-get install -y locales
RUN apt-get install -y gettext gettext-doc libgettextpo-dev

RUN apt-get install -yq \
    git \
    zip \
    libfreetype6-dev \
    libmcrypt-dev \
    libjpeg-dev \
    libicu-dev \
    libgettextpo-dev \
    libpng-dev

RUN docker-php-ext-install pdo_mysql \
    gd \
    mbstring \
    mysqli \
    gettext \
    intl

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN locale-gen en_US.UTF-8
RUN locale-gen pt_BR.UTF-8
RUN locale-gen ru_RU.UTF-8

RUN chown -R www-data:www-data /var/www