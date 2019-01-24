FROM php:apache

# Install Postgre PDO
RUN apt-get update && apt-get install -y build-essential libpq-dev curl gnupg gnupg2 gnupg1 && docker-php-ext-install pdo pdo_pgsql

# Using Debian, as root
RUN curl -sL https://deb.nodesource.com/setup_11.x | bash -
RUN apt-get install -y nodejs

RUN a2enmod rewrite
