FROM php:fpm-alpine

RUN apk add --update \
    autoconf \
    g++ \
    libtool \
    make

RUN docker-php-ext-install pdo_mysql

RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis

RUN apk del \
    autoconf \
    g++ \
    gcc \
    libtool \
    make \
    && rm -rf /tmp/* /var/cache/apk/*


CMD ["php-fpm"]

EXPOSE 9000