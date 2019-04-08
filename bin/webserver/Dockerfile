FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update
RUN apt-get upgrade -y

# Install useful tools
RUN apt-get -y install software-properties-common
RUN apt-get -y install apt-utils git wget
RUN add-apt-repository ppa:ondrej/php
RUN apt-get -y update --fix-missing

# Install important libraries
RUN apt-get -y install --fix-missing build-essential libcurl4 curl zip openssl

# Install memcached
RUN apt-get -y install memcached

# Install php
RUN apt-get install -y \
    php7.1 \
    php7.1-cli \
    php7.1-common \
    php7.1-curl \
    php-date \
    php7.1-dev \
    php7.1-dom\
    php7.1-enchant \
    php7.1-exif \
    php7.1-gmp \
    php7.1-imap \
    php7.1-imagick \
    php7.1-interbase \
    php7.1-intl \
    php7.1-json \
    php7.1-ldap \
    libxml2 \
    php7.1-mbstring \
    php7.1-mcrypt \
    php7.1-memcached \
    php7.1-mysql \
    php7.1-odbc \
    php7.1-opcache \
    php7.1-PDO \
    php7.1-pgsql \
    php7.1-phpdbg \
    php7.1-pspell \
    php7.1-readline \
    php7.1-recode \
    php7.1-snmp \
    php7.1-SimpleXML \
    php7.1-sybase \
    php7.1-tidy \
    php7.1-xml \
    php7.1-xmlrpc \
    php7.1-xmlreader \
    php7.1-xmlwriter \
    php7.1-xsl \
    php7.1-zip

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Other PHP7 Extensions
RUN apt-get -y install mysql-client

# Install apache
RUN apt-get install apache2 libapache2-mod-php7.1 -y
RUN apt-get install postfix -y

# Install node environment
RUN apt-get install git nodejs npm -y
RUN npm install -g gulp tsd

# Enable apache modules
RUN a2enmod rewrite headers

ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
