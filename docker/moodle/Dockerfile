FROM alpine
MAINTAINER Yevhen Matasar <matasar.ei@gmail.com>

RUN apk add --update --no-cache \
            git \
            curl \
            php5 \
            php5-apache2 \
            php5-ctype \
            php5-curl \
            php5-dom \
            php5-gd \
            php5-iconv \
            php5-intl \
            php5-json \
            php5-mysqli \
            php5-openssl \
            php5-soap \
            php5-xml \
            php5-xmlreader \
            php5-xmlrpc \
            php5-zip \
            php5-zlib \
            apache2 \
            apache2-utils

RUN  rm -rf /var/cache/apk/*

RUN sed -i "s#/var/www/localhost/htdocs#/var/www/moodle#g" /etc/apache2/httpd.conf

RUN mkdir -p /run/apache2 && \
    mkdir /var/www/moodle && \
    chown apache:apache /var/www/moodle && \
    mkdir /var/www/moodledata && \
    chown apache:apache /var/www/moodledata

VOLUME  /var/www/moodle/
WORKDIR  /var/www/moodle/

EXPOSE 80
EXPOSE 443

CMD /usr/sbin/httpd -D FOREGROUND
