# Docker for installing Symfony 

Only for DEV, not for production!

**Docker + PHP 8.1 + MySQL 8 + Nginx + XDebug 3.1.2 + Adminer**

## Setup

See hostnames in the `.env` file.

Add to `/etc/hosts` file lines:
```
127.0.0.1 docker-symfony.test
127.0.0.1 adminer.test
```
Clone and run the `docker-compose`:
```
git clone https://github.com/amberlex78/docker-symfony
cd docker-symfony
make init
```

Log into the PHP container
```
docker-compose exec php bash
```

## Install Symfony

Execute the following commands in a container.

To install the latest stable version:

```
symfony new . --full
or
symfony new . --full --version=stable
```

To install the current LTS version:
```
symfony new . --full --version=lts
```

To install a specific version:
```
symfony new . --full --version=5.4
```

## Check version
```
symfony console -V
```
```
bin/console -V
```
```
s -V
```

Result:
```
Symfony 6.0.1 (env: dev, debug: true)
```

## Config

Execute the following command on your computer.

```
sudo chown -R $USER:$USER project/
cp project/.env project/.env.local
```

See database connection parameters in the `.env` file.

Database connection in the `project/.env.local` file:
```
DATABASE_URL="mysql://symfony:symfony@mysql:3306/symfony?serverVersion=8.0"
```

## Access to site
```
http://docker-symfony.test
```
