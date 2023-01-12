ARG php_version

FROM php:${php_version}

RUN apt-get update
RUN apt-get install -y \
        libfreetype6-dev \
        libmcrypt-dev \
        libjpeg-dev \
        libpng-dev

RUN docker-php-ext-install \
        pdo \
        pdo_mysql \
        mysqli

RUN docker-php-ext-configure gd \
        #--enable-gd-native-ttf \
        --with-freetype-dir=/usr/include/freetype2 \
        --with-png-dir=/usr/include \
        --with-jpeg-dir=/usr/include
RUN docker-php-ext-install gd \
    && docker-php-ext-install mbstring \
    && docker-php-ext-enable gd

RUN a2enmod rewrite