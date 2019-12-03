FROM ubuntu:14.04

# Maintainer
LABEL maintainer="Fábio Massalino"

RUN apt-get update && apt-get install -y apache2 apache2-utils  php5 libapache2-mod-php5 && apt-get clean

#php
RUN mkdir -p /var/html/php
ADD ./index.php /var/www/html/php/index.php
#SSL
RUN a2enmod ssl
ADD ./ssl/ /etc/apache2/ssl
ADD ./apache2.conf /etc/apache2/apache2.conf
ADD ./admweb.com.br.conf /etc/apache2/sites-available/000-default.conf
# BUILD
WORKDIR /var/www/html
EXPOSE 80 443
CMD /usr/sbin/apache2ctl -D FOREGROUND                                                        