FROM php:7.1-apache
RUN apt-get update && \
    apt-get install -y \
    zlib1g-dev \
    && docker-php-ext-install pdo_mysql mysqli mbstring zip \
    && a2enmod rewrite

COPY --from=composer /usr/bin/composer /usr/bin/composer
