FROM gliderlabs/alpine:latest
MAINTAINER kan
# timezone for OS
RUN apk --update add tzdata && \
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  apk del tzdata && \
  rm -rf /var/cache/apk/*
# install Apache2+PHP
RUN apk --no-cache add apache2 php-apache2 \
  php php-fpm php-json php-zlib php-xml php-pdo php-phar \
  php-openssl php-curl php-pdo_mysql php-mysql php-mysqli \
  php-gd mysql-client \
    && mkdir -p /run/apache2/
# timezone for PHP
RUN echo 'date.timezone = Asia/Tokyo' > /etc/php/conf.d/timezone.ini
COPY httpd-develop.conf /etc/apache2/conf.d/
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]
