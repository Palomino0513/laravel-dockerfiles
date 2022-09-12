FROM php:8.2-rc-fpm

# Install Postgre PDO
RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y --no-install-recommends \
		build-essential \
		libpq-dev \
		curl \
		gnupg \
		gnupg2 \
		gnupg1 \
		zip \
		git \
		unzip \
		libzip-dev \
		libfreetype6-dev \
		libjpeg62-turbo-dev \
		libmemcached-dev \
	    libz-dev \
	    libpq-dev \
	    libjpeg-dev \
	    libpng-dev \
	    libfreetype6-dev \
	    libssl-dev \
		libmcrypt-dev \
		&& rm -rf /var/lib/apt/lists/*

# Install the PHP pdo_mysql extention
RUN docker-php-ext-configure zip \
	&& docker-php-ext-install pdo pdo_pgsql zip \
	&& docker-php-ext-configure gd \
	&& docker-php-ext-install gd

RUN apt-get update && apt-get install -y libxml2-dev \
    && pear install -a SOAP-0.13.0 \
    && docker-php-ext-install soap;

# install composer
RUN curl -sSL --show-error https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html
