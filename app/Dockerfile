FROM gliderlabs/alpine:latest
MAINTAINER kan
RUN apk --update add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata && \
    rm -rf /var/cache/apk/*
RUN mkdir -p /var/www/app
ADD laravel /var/www/app/current
RUN chown -R 1000 /var/www/app/current/storage
VOLUME /var/www/app/current
#CMD /bin/sh # $ docker run -it --name test -v /hoge laravel/test sh
