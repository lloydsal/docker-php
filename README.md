# docker-php

This project is a base Docker environment for PHP development using a basic setup.

# Requirements

1. Docker Engine 19.03.0+

# Containers / Softwares Provided

1. PHP FPM 7.3
2. Nginx 1.19
3. Mysql 5.7
4. PHP Composer Latest

# Setup

1. Add `127.0.0.1 myphp.local` to your `/etc/hosts` file
2. Start containers using `docker-compose up -d`

# Usage

## Access from browser

Start the container using `docker-compose up -d` Then access the website using [http://myphp.local:8080](http://myphp.local:8080)

## PHP Container

### Connect to the php container 
```bash
docker-compose exec php /bin/bash
```

### Running Composer 
1. connect to the php container
2. Run composer as normal
```
composer install
```

## Connecting to Database

To connect from your host machine
```
mysql -h 127.0.0.1 -u root -P 33060 -p
```

To connect from the PHP container
```
mysql -h mysql -u root -p
```

