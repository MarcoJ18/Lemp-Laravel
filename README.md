# Lemp-Laravel
This if for install lemp stack with laravel 

Version of Services
------------------


| **Service** | **Version** |
|-------------|-------------|
| Nginx       |             |
| MySQL       |             |
| PHP         |   8.1       |
| Node        |             |
| Composer    |             |
| NPM         |             |



<hr>

## Start
```bash
sudo apt update -y && sudo apt upgrade -y
```

Install PHP
-----------

This is all packet you need for PHP with Laravel because laravel need if only install PHP you don't need all this packet  

```bash
sudo apt-get install software-properties-common -y

sudo add-apt-repository ppa:ondrej/php -y

sudo apt-get update -y

sudo apt-get install php8.1 php8.1-mbstring php8.1-gettext php8.1-zip php8.1-fpm php8.1-curl php8.1-mysql php8.1-gd php8.1-cgi php8.1-soap php8.1-sqlite3 php8.1-xml php8.1-redis php8.1-bcmath php8.1-imagick php8.1-intl -y 

sudo apt-get install php8.1-fpm php8.1-mysql php8.1-mbstring unzip  php8.1-bcmath php8.1-zip php8.1-gd php8.1-tokenizer php8.1-xml -y

sudo apt install php8.1-cli unzip -y

```

If you need and use <b>php the lastest version</b> install this packet:
```bash
sudo apt install php-json
```

Check
```bash
php -v
sudo systemctl status php8.1-fpm
```


Install MySQL
-------------

Install MySQL with a segure password if you want to use a not secure password then need to change the security of mysql

 - Password Example: **i6EuP9RmO41$** 

```bash
sudo apt install mysql-server -y

sudo mysql
````
```mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'yourpassword';

exit;
````
````bash
sudo mysql_secure_installation
````
Press all Enter this not important if you want to read and press you want you are free to make

This part if for laravel because i create the database and the user for laravel you can skip this part if you don't need database bacuse you already you have

```bash
mysql -u root -p
````

Change the name of database and the user , password with your own database name , user and password:

```mysql
CREATE DATABASE yourdatabase;

use marco;

CREATE USER username@'%' IDENTIFIED BY 'yourpassword';

GRANT ALL ON yourdatabase.* TO username@'%';

FLUSH PRIVILEGES;
```
Check 
```bash
mysql -v
sudo systemctl status myslq-server

```


Install composer
----------------

Now you install Composer the packet manager for laravel you can install with 3 method :

- Method 1

  With the git repo:
  ```bash
  sudo apt-get install git composer -y
  ```

- Method 2

  The installer of official web you need curl `sudo apt install -y curl`:

  ```bash
  curl -sS https://getcomposer.org/installer | php 
  ```
  
- Method 3

  The official install of composer web this check is has the same hash_file

  ```bash

  php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
  php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo   'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
  php composer-setup.php
  php -r "unlink('composer-setup.php');"

  ```

When you install with one of this method then you need to put in bin for gobally composer: 

```bash
sudo mv composer.phar /usr/local/bin/composer
```
Check the version
```bash
composer -v
```


Install Node & NPM
------------------

I install `Node` and `NPM` because i use in my project but you can skip and install laravel directly

If you install follow the next step:

You install node 12 in the first instalation:

```bash
sudo apt install nodejs
sudo apt install npm
```

This for install node 12 to node 18 maybe you have and error:

```bash
sudo apt install -y curl

curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

To solve this error you need to use this:
```bash
sudo dpkg -i --force-overwrite /var/cache/apt/archives/nodejs_18.16.0-deb-1nodesource1_amd64.deb

sudo apt -f install

sudo apt install -y nodejs
````

Check the version
```bash
node -v
npm -v
```



Install Laravel
---------------


Install Nginx
-------------

sudo apt install nginx



https://askubuntu.com/questions/1062171/dpkg-deb-error-paste-subprocess-was-killed-by-signal-broken-pipe

https://joshtronic.com/2022/04/24/how-to-install-nodejs-18-on-ubuntu-2004-lts/

https://alfaexploit.com/es/posts/you_are_not_allowed_to_create_a_user_with_grant/

https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04

https://stackoverflow.com/questions/50177216/how-to-grant-all-privileges-to-root-user-in-mysql-8-0

https://www.iankumu.com/blog/how-to-deploy-a-laravel-app-on-lemp-stack/

https://techvblogs.com/blog/deploy-laravel-project-nginx-ubuntu

https://arnoldfederis.medium.com/how-to-install-lemp-stack-and-deploy-your-laravel-application-in-digitalocean-ubuntu-20-04-67c66cc2275c

https://qirolab.com/posts/how-to-install-laravel-with-lemp-stack-on-ubuntu-1604490338



