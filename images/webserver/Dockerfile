FROM ubuntu:trusty

MAINTAINER Ryan Bishop <dreamchimney@gmail.com>

RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Only use stable sources
RUN rm -rf /etc/apt/sources.list.d/proposed.list

# Install packages
RUN apt-get update && \
  apt-get install -y \
  curl \
  wget \
  nano \
  php5-fpm \
  php5-mysql \
  php5-mcrypt \
  php5-gd \
  php5-curl \
  php5-xdebug

#RUN curl -sS https://getcomposer.org/installer | php
#RUN mv composer.phar /usr/local/bin/composer

# Create required directories
RUN mkdir -p /etc/nginx && \
    mkdir -p /var/run/php5-fpm && \
    mkdir -p /etc/nginx/sites-enabled 

RUN rm -rf /etc/nginx/sites-available/default

# Add configuration files
ADD php.ini /etc/php5/fpm/conf.d/40-custom.ini

# Expose volumes
VOLUME ["/var/www", "/etc/nginx/sites-enabled"]

EXPOSE 80

WORKDIR /var/www

CMD service php5-fpm start && nginx