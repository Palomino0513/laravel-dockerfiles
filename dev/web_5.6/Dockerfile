FROM php:5.6-apache

# Install Postgre PDO
RUN apt-get update \
  && apt-get install -y git zlib1g-dev \
  && docker-php-ext-install -j$(nproc) pdo pdo_mysql zip mysql mysqli \
  && docker-php-ext-enable pdo pdo_mysql

RUN a2enmod rewrite
