FROM gliderlabs/alpine:latest
MAINTAINER kan
RUN apk --no-cache add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
RUN mkdir -p /var/www/app
ADD laravel /var/www/app/current
RUN chown -R 1000 /var/www/app/current/storage
VOLUME /var/www/app/current
