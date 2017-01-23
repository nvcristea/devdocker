FROM alpine:3.5

MAINTAINER Nicolae V. Cristea <coder@cristea.bid>

# ensure www-data user exists
RUN set -x \
	&& addgroup -g 82 -S www-data \
	&& adduser -u 82 -D -S -G www-data www-data
# 82 is the standard uid/gid for "www-data" in Alpine

RUN apk add --update --no-cache \
        nano curl \
        apache2 \
        apache2-utils \
        php5-apache2 \
        php5-cli \
        php5-mysql \
        php5-json \
        php5-soap \
        php5-mcrypt \
        php5-openssl \
        php5-curl \
        php5-gd \
        php5-apcu \
        php5-iconv \
        php5-dom \
        php5-xmlreader \
        php5-xmlrpc \
        php5-xcache \
        php5-zip \
        php5-pdo_mysql \
        php5-gettext \
        php5-bz2 \
        php5-memcache \
        php5-ctype \
        php5-phar \
        php5-xdebug && \
    sed -i 's#^DocumentRoot ".*#DocumentRoot "/var/www/html"#g' /etc/apache2/httpd.conf && \
    sed -i 's#AllowOverride None#AllowOverride All#' /etc/apache2/httpd.conf && \
    sed -i 's/^#ServerName.*/ServerName httpd-php56.dev/' /etc/apache2/httpd.conf && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY httpd-foreground.sh /usr/local/bin/httpd-foreground
COPY httpd-extra.conf /etc/apache2/conf.d/

EXPOSE 80
CMD ["httpd-foreground"]
