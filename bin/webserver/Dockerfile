FROM php:7.3-apache

RUN apt-get -y update --fix-missing
RUN apt-get upgrade -y

# Install useful tools
RUN apt-get -y install apt-utils nano wget dialog vim nano

# Install important libraries
RUN apt-get -y install --fix-missing apt-utils build-essential git curl libcurl3-dev zip openssl

# Other PHP7 Extensions
RUN apt-get -y install libsqlite3-dev libsqlite3-0 mariadb-client
# RUN docker-php-ext-install pdo_mariab 
# RUN docker-php-ext-install mysqli
# RUN docker-php-ext-install pdo_sqlite
# RUN docker-php-ext-install curl
RUN docker-php-ext-install tokenizer
RUN docker-php-ext-install json

# RUN apt-get -y install lib-zip
# RUN docker-php-ext-install zip

RUN apt-get -y install libicu-dev
RUN docker-php-ext-install -j$(nproc) intl

RUN docker-php-ext-install mbstring
RUN docker-php-ext-install gettext

RUN apt-get -y install gcc make autoconf libc-dev pkg-config 
RUN apt-get -y install libxml2-dev

RUN docker-php-ext-configure intl 
RUN docker-php-ext-configure xmlrpc 
RUN docker-php-ext-configure soap
RUN docker-php-ext-install intl
RUN docker-php-ext-install xmlrpc
RUN docker-php-ext-install soap

RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install -j$(nproc) gd

# Enable apache modules
RUN a2enmod rewrite headers

RUN git clone https://github.com/moodle/moodle.git -b MOODLE_37_STABLE development /var/www/html/