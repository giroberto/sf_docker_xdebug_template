FROM php:8-cli-alpine

RUN pecl channel-update pecl.php.net
RUN pecl config-set php_ini "${PHP_INI_DIR}/php.ini"
RUN apk add --no-cache $PHPIZE_DEPS
COPY xdebug-3.0.4.tgz /tmp/
RUN pecl install /tmp/xdebug-3.0.4.tgz
COPY 90-xdebug.ini "${PHP_INI_DIR}/conf.d"

EXPOSE 8000

CMD pwd && ls -l && cd /demo && php -d display_errors=0 -S 0.0.0.0:8000 -t public/