FROM php:apache

# Install Postgre PDO
RUN apt-get update && apt-get install -y build-essential libpq-dev git curl gnupg gnupg2 gnupg1 && docker-php-ext-install pdo pdo_pgsql

# install composer
RUN curl -sSL --show-error https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install node and npm
RUN curl -sSL --show-error https://deb.nodesource.com/setup_11.x | bash -
RUN apt-get install -y nodejs

RUN a2enmod rewrite
