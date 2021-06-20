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

#COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

RUN curl --silent --show-error https://getcomposer.org/installer | php \
	&& mkdir -p /usr/local/bin \
	&& mv composer.phar /usr/local/bin/composer \
	&& chmod +x  /usr/local/bin/composer

RUN mkdir -p /.composer && chmod 777 /.composer
