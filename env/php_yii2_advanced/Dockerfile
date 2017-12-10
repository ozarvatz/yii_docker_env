############################################################
# Dockerfile to build mysql container images
# Based on oraclelinux:latest
############################################################

# Set the base image to Ubuntu
FROM env_appachphp

# File Author / Maintainer
MAINTAINER Oz Arvatz <oz.arvatz@gmail.com>

RUN apt-get update -y
RUN apt-get install sudo -y
RUN apt-get install nano -y
#should move to a different container 
VOLUME /var/www/html/
ADD html/apache2.conf /etc/apache2/apache2.conf
ADD html/000-default.conf sites-available/000-default.conf
#RUN chown -R www-data:www-data /var/www/html/
RUN chmod -R 755 /var/www/html/
WORKDIR /var/www/html/yii2advances/advanced

RUN a2enmod rewrite
RUN service apache2 restart