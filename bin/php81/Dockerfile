FROM php:8.1-apache

ARG TZ

RUN cp /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt update
RUN apt install -y tzdata
RUN apt install -y nano
RUN apt install -y cron
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN docker-php-ext-install pdo_mysql && \
    docker-php-ext-install exif 

RUN echo ALL >> /etc/cron.allow
# RUN crontab /etc/cron.d/cron

# RUN service cron start
# CMD service cron status
