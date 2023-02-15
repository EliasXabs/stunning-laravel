 <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>
 
>ip : [172.31.33.114](http://172.31.33.114)

# Findings
> ## Sudo
> Sudo is a way to ask for the user to enter the password for admin access on the task

>## apt-get
>apt-get is used to install packages onto ur machine/server


>Checkpoint 4 : Used cp to copy files

>chgrp : Changes the ownership of a the folder\
>chmod : Changes the permissions of a file


># How to deploy a server:
>## Connecting to the server and downloading its specific packages:
>
> - `ssh -i urkey.pem ubuntu@address`
> - `apt-get the packages`
> - `a2enmod rewrite`
> - restart apache2 using `sudo /etc/init.d/apache2 restart`
>
>## Uploading the website onto the server
>
> - `git clone therepo` in `var/www/html` if it doesn't exist create it
>
>## Install composer
>
> - run `curl -sS https://getcomposer.org/installer | sudo php -- --install-
dir=/usr/local/bin --filename=composer` to install it
> - run `composer i` in the repo (if u can find the file composer.json pre-ruunning)
>
>## Creating your app environment and generating a key
>
> - copy the `.env.example` and change its name to `.env`
> - now `vim .env` and change the app name to your preferences (don't use whitespaces)
> - run `php artisan key:generate`
>
>## Configuring apache2
>
> - find its path
> - `vim apache2.conf` and add ur website directory
> - `cd sites-enabled`
> - `vim 000-default.conf` add your admin and the website root
> - restart apache2 using `sudo /etc/init.d/apache2 restart`
>
>## Setting up the folders
>
> - go to the repository
> - run `sudo chgrp -R www-data storage bootstrap/cache`
> - run `sudo chmod -R ug+rwx storage bootstrap/cache`
> - now your website should be public and availble for people to visit !!!
