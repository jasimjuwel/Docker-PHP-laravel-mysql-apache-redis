FROM php:7.2.5-apache

ARG uid

RUN useradd -G www-data,root -u $uid -d /home/duser duser

RUN mkdir -p /home/duser/.composer && \
    chown -R duser:duser /home/duser

RUN apt-get update --fix-missing -q

RUN apt-get install -y openssl zip unzip git libonig-dev  libxml2-dev libpng-dev libjpeg-dev libfreetype6-dev libonig-dev curl mcrypt gnupg build-essential software-properties-common wget vim libwebp-dev
RUN curl -sL https://deb.nodesource.com/setup_14.x  | bash -
RUN apt-get -y install nodejs

RUN  docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-webp-dir=/usr/include/  --with-jpeg-dir=/usr/include

RUN docker-php-ext-install zip mysqli mbstring pdo pdo_mysql tokenizer xml bcmath opcache pcntl intl soap exif gd

RUN curl -sSL https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public

ENV APACHE_LOG_DIR /var/log/apache2

ENV APACHE_RUN_DIR /var/run/apache2

ENV APACHE_LOCK_DIR /var/lock/apache2

ENV APACHE_PID_FILE /var/run/apache2/apache2.pid

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN a2enmod rewrite

COPY . /var/www/html/

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]
