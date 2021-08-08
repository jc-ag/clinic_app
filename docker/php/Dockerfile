ARG php_version

FROM php:${php_version}

RUN apt-get update -y && apt-get install -y libpng-dev
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN a2enmod rewrite
RUN docker-php-ext-install gd
