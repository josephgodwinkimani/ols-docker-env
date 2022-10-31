FROM ubuntu:20.04
USER root
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get wget
FROM litespeedtech/openlitespeed:1.7.16-lsphp74
WORKDIR /usr/bin
# RUN apt-get install lsphp74-apcu lsphp74-curl lsphp74-imagick lsphp74-json lsphp74-memcached lsphp74-mysql lsphp74-pear lsphp74-pspell lsphp74-redis -y
ENV COMPOSER_ALLOW_SUPERUSER=1
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php && mv composer.phar /usr/local/bin/composer && php -r "unlink('composer-setup.php');"
RUN wget -q https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && mv wp-cli.phar /usr/local/bin/wp-cli && chmod +x /usr/local/bin/wp-cli && mkdir -p /nonexistent/.wp-cli/cache && chown -R nobody:nogroup /nonexistent/.wp-cli


