# Installation of webshop

Open Powershell (PS) or other Terminal (prompt my be different then).

## Starting Docker and install Repo

See [fhooe-web-dock](https://github.com/Digital-Media/fhooe-web-dock)

```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html && git clone https://github.com/Digital-Media/webshop.git && chmod 777 webshop"
```
```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html/webshop && composer install && chmod -R 777 *"
```
```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html/webshop && composer update"
```

## Maintaining a database in Container mariadb
`PS path-to-Docker/Docker/fhooe-web-dock> `
```shell
docker exec -it mariadb /bin/bash -c "mariadb -uonlineshop -pgeheim"
```
```shell
 Welcome to the MariaDB monitor.  Commands end with ; or \g.
 Your MariaDB connection id is 7
 Server version: 10.7.1-MariaDB-1:10.7.1+maria~focal mariadb.org binary distribution

 Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

 Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

 MariaDB [(none)]> drop database onlineshop;
 Query OK, 11 rows affected (0.229 sec)

 MariaDB [(none)]> 
 ```
```shell
 show databases;
```
```shell
 +--------------------+
 | Database           |
 +--------------------+
 | information_schema |
 +--------------------+
 1 row in set (0.001 sec)

 MariaDB [(none)]> 
```
```shell
 exit
```
`PS path-to-Docker/Docker/fhooe-web-dock> `

## Vagrant

See [fhooe-webdev](https://github.com/Digital-Media/fhooe-webdev)

```shell
vagrant ssh
```
```shell
cd /var/www/html/code
```
```
git clone https://github.com/Digital-Media/webshop.git
```
```shell
cd webshop
```
```shell
composer install
```

# Running the Webshop Docker on M1 Macs

## 1. Install homebrew

Homebrew is a package manager (like pip or npm) that we can use to install... well... stuff. But in order to install stuff with homebrew, we first have to install Homebrew itself.

To do that, use this command in a Terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

If that doesnt work, check the [Homebrew homepage](https://brew.sh)

## 2. Install Composer

Now we use Homebrew to install Composer, which we need to work with all the Twig goodness.

```bash
/opt/homebrew/bin/brew install composer
```

## 3. Navigate to the Webdock Repo

Make sure you are in the ``` fhooe-web-dock/webapp/ ``` directory.

The problem is that we currently can't run git via ```docker exec```. Fine, we'll do it ourselves. We are going to execute the three commands found in the [Install Instructions](https://github.com/Digital-Media/webshop/blob/main/INSTALL.md) by hand. Btw, we don't use the prebuilt images (currently) but rather we use the verified images from Docker Hub.

## 4. Execute them all

Essentially, we're just copying the part after the ```&&``` out of the instruction commands.

First we'll clone the repo:

```bash
git clone https://github.com/Digital-Media/webshop.git
```

Then we have to install all the composer packages (you might remember us using ```npm install``` when we did the Gulp stuff in first semester. This is basically the same thing):

```bash
composer install
```

Optionally (just to be sure) we can run

```bash
composer update
```

to make sure everything is up do date use http://localhost:8083 to access the webshop.

Now it should work... i hope
