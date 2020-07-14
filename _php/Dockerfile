FROM php:7.3-fpm

RUN apt-get update && \
    apt-get install -y \
        git \
        curl \
        libfreetype6-dev \
        libjpeg-dev \
        libpng-dev \
        libonig-dev \
        libxml2-dev \
        libxslt1-dev \
        libzip-dev \
        zip \
        unzip

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install \
        bcmath \
        gd \
        hash \
        intl \
        mbstring \
        opcache \
        pdo_mysql \
        soap \
        sockets \
        xsl \
        zip

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN useradd -G www-data,root -d /home/magento magento
RUN mkdir -p /home/magento/.composer && \
    chown -R magento:magento /home/magento

WORKDIR /var/www/html

USER magento