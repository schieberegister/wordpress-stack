FROM alpine:latest


LABEL maintainer="hb@beohof.de"

RUN adduser -D -g 'www' www

RUN apk add --no-cache nginx \
supervisor \
php7  \
php7-fpm  \
php7-opcache \
php7-common \
php7-iconv \
php7-json \
php7-gd \
php7-curl \
php7-xml \
php7-mysqli \
php7-imap \
php7-cgi \
php7-pdo \
php7-pdo_mysql \
php7-soap \
php7-xmlrpc \
php7-posix \
php7-mcrypt \
php7-gettext \
php7-ldap \
php7-ctype \
php7-dom

RUN mkdir /www && \
chown -R www:www /var/lib/nginx && \
chown -R www:www /www


COPY config/nginx.conf /etc/nginx/nginx.conf
COPY config/supervisord.conf /etc/supervisord.conf
COPY config/php-fpm.conf /etc/php7/php-fpm.conf
COPY config/php.ini /etc/php7/php.ini

ENTRYPOINT ["supervisord"]
EXPOSE 80
