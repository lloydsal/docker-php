# docker-php

This project is a base Docker environment for PHP development using a basic setup.

# Requirements

1. Docker Engine 19.03.0+

# Containers / Softwares Provided

1. PHP FPM 7.3
2. Nginx 1.19
3. Mysql 5.7
4. MemcacheD Latest
5. PHP Composer Latest

# Setup

1. Add `127.0.0.1 mysite.local` to your `/etc/hosts` file
2. Start containers using `docker-compose up -d`

# Usage

## Access from browser

Start the container using `docker-compose up -d` Then access the website using [http://mysite.local](http://myphp.local)

*note: If port 80 is being used by some other application change `"80:80"` to `8080:80` in `docker-compose.yml` and connect to [http://mysite.local:8080](http://myphp.local:8080) instead*

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

### Making a request to self
To make a request to the own site inside the container use host `nginx`
```
curl 'http://nginx/index.php'
```

*This is helpful for API tests*

## Connecting to Database

To connect from your host machine
```
mysql -h 127.0.0.1 -u root -P 33060 -p
```

To connect from the PHP container
```
mysql -h mysql -u root -p
```

