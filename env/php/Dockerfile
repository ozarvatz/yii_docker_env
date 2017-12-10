############################################################
# Dockerfile to build mysql container images
# Based on oraclelinux:latest
############################################################

# Set the base image to Ubuntu
FROM php:5.6.29-apache

# File Author / Maintainer
MAINTAINER Oz Arvatz <oz.arvatz@gmail.com>
# install extension 
RUN apt-get update
RUN apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        php5-gd \
        php5-mysql \
        # cron \
        # libapache2-mod-php5 \
        # php5.6-bcmath \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    &&  curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer 

RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install bcmath
# Install software 
RUN apt-get install -y unzip
RUN apt-get install -y git
RUN apt-get install -y apt-utils
# RUN apt-get install -y cron

# Make ssh dir
RUN mkdir /root/.ssh/

