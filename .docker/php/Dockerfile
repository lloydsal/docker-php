FROM php:7.3-fpm

# upgrade Repositories
RUN apt-get update && apt-get install -y

# install mysql/MariaDB Client
RUN apt-get install -y mariadb-client

# For DB Access from container
RUN docker-php-ext-install mysqli pdo pdo_mysql

# install text editors, other utils
RUN apt-get install -y nano vim htop

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
