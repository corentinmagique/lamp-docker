FROM php:8.1-apache

ENV TZ=Indian/Reunion

RUN cp /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt update
RUN apt install -y tzdata
RUN apt install -y nano
RUN apt install -y cron
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN docker-php-ext-install pdo_mysql && \
    docker-php-ext-install exif 

RUN echo ALL >> /etc/cron.allow
# RUN service cron start
# CMD service cron status
# RUN echo "* * * * * echo 'Cron running !' >> /var/log/apache2/error.log" >> /var/spool/cron/crontabs/root
