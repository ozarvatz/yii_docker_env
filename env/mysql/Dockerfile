############################################################
# Dockerfile to build mysql container images
# Based on oraclelinux:latest
############################################################

# Set the base image to Ubuntu
FROM oraclelinux:latest

# File Author / Maintainer
MAINTAINER Oz Arvatz <oz.arvatz@gmail.com>

ENV PACKAGE_URL https://repo.mysql.com/yum/mysql-8.0-community/docker/x86_64/mysql-community-server-minimal-8.0.0-0.1.dmr.el7.x86_64.rpm
# ENV PACKAGE_URL https://repo.mysql.com/yum/mysql-8.0-community/docker/x86_64/mysql-community-server-minimal-8.0.0-0.1.dmr.el7.x86_64.rpm

# Install server
RUN rpmkeys --import http://repo.mysql.com/RPM-GPG-KEY-mysql \
  && yum install -y $PACKAGE_URL \
  && yum install -y libpwquality \
  && rm -rf /var/cache/yum/*
RUN mkdir /docker-entrypoint-initdb.d

RUN chown -R mysql:mysql /var/lib/mysql
RUN chmod -R 0777 /var/lib/mysql

RUN mkdir /backup
# VOLUME /var/lib/mysql


COPY docker-entrypoint.sh /entrypoint.sh
# RUN chown -R mysql:mysql /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 3306 33060
CMD ["mysqld"]