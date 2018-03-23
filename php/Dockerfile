FROM php:7.2-fpm-alpine

COPY ./ext/xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

RUN composer config -g repo.packagist composer https://packagist.phpcomposer.com

RUN mkdir /app

RUN addgroup -g 1000 -S ${APPLICATION_USER_NAME} \
	&& adduser -u 1000 -D -S -G ${APPLICATION_USER_NAME} ${APPLICATION_USER_NAME}

RUN chown ${APPLICATION_USER_NAME}:${APPLICATION_USER_NAME} /app

USER ${APPLICATION_USER_NAME}

WORKDIR /app
