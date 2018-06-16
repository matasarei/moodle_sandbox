FROM alpine
MAINTAINER Yevhen Matasar <matasar.ei@gmail.com>

RUN apk add --update --no-cache \
            git \
            curl \
            php7 \
            php7-apache2 \
            php7-ctype \
            php7-curl \
            php7-dom \
            php7-fileinfo \
            php7-gd \
            php7-iconv \
            php7-intl \
            php7-json \
            php7-mbstring \
            php7-mysqli \
            php7-openssl \
            php7-session \
            php7-simplexml \
            php7-soap \
            php7-tokenizer \
            php7-xml \
            php7-xmlreader \
            php7-xmlrpc \
            php7-zip \
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
