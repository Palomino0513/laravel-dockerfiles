FROM php:7.3-fpm

# Install packages
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
RUN docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install mysqli pdo pdo_mysql zip \
	&& docker-php-ext-configure gd \
		--with-jpeg-dir=/usr/lib \
		--with-freetype-dir=/usr/include/freetype2 && \
	docker-php-ext-install gd

RUN apt-get update && apt-get install -y libxml2-dev \
    && pear install -a SOAP-0.13.0 \
    && docker-php-ext-install soap;

# install composer
RUN curl -sSL --show-error https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install node and npm
RUN curl -sSL --show-error https://deb.nodesource.com/setup_11.x | bash -
RUN apt-get install -y nodejs

WORKDIR /var/www/html
