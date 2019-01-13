FROM php:7.3.0-fpm

WORKDIR /var/www/html

COPY ./shell/.bashrc /root/.bashrc

RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y iproute2
RUN apt-get install -y iputils-ping

RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mbstring

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('sha384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv /var/www/html/composer.phar /usr/local/bin/composer