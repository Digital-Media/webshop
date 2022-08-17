# Installation of webshop

Open Powershell (PS) or other Terminal (prompt my be different then).

## Starting Docker

See [fhooe-web-dock](https://github.com/Digital-Media/fhooe-web-dock)

### Using Prebuilt images

If you use private repos built by [Upper Austria University of Applied Sciences (FH Oberösterreich), Hagenberg Campus](https://www.fh-ooe.at/en/hagenberg-campus/).

```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html && git clone https://github.com/Digital-Media/webshop.git"
```
```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html/webshop && composer install"
```
```shell
docker exec -it webapp /bin/bash -c "cd /var/www/html/webshop && composer update"
```
### Using verified images from Docker Hub and build layers during docker compose up -d

To use varified images from [Docker Hub](htts://hub.docker.com) with layers built during docker compose up -d

```shell
docker exec -it webapp-l /bin/bash -c "cd /var/www/html && git clone https://github.com/Digital-Media/webshop.git"
```
```shell
docker exec -it webapp-l /bin/bash -c "cd /var/www/html/webshop && composer install"
```
```shell
docker exec -it webapp-l /bin/bash -c "cd /var/www/html/webshop && composer update"
```

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
