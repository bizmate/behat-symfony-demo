FROM php:7.1-cli
# WORKDIR "/application"

# Install selected extensions and other stuff
RUN apt-get update && apt-get install -y  libcurl4-gnutls-dev git zip \
	libfreetype6-dev libmcrypt-dev libicu-dev libpq-dev \
	&& docker-php-ext-install curl \
	&& docker-php-ext-install mysqli pdo_mysql pcntl\
	&& docker-php-ext-install -j$(nproc) mcrypt \
	&& apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
