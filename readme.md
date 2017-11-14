# Setting PHP MySql and composer dependency manager in ubuntu.

### blah blah ....
Before installing php and mysql I wish you should know how to use nice looking `zsh` terminal in ubuntu. Where you will get .zshrc file. Which will load every time you open your terminal. Here is the youtube link. Here is Github link. Benefit of .zshrc file is, you can easily make alias and add file to path variable.

## tuts
I am using ubuntu for last 2 years for php development. I feel like ubuntu is amazing. Therefore, lot of people not using ubuntu because of some complexity of command line installation. In this video I have showed how to install `PHP` `Mysql` and `composer`  dependency manger. And How can you further configure `PHP` `mysql` and `composer`.

### Installing xampp in Ubuntu
download xampp.run file from their official website. After downloading file install xampp by following code.
~~~
sudo chmod +x <Your_xamppfile.run>
sudo ./<Your_xamppfile.run>
~~~
xampp doesn't comes with desktop entry. So what we can do ? We can add a alias following in your `~/.bashrc` or `~/.zshrc` file
~~~
alias xampp="sudo /opt/lampp/manager-linux-x64.run"
~~~

To give permission htdocs recursively
~~~
sudo chmod 777 -R htdocs
~~~

### How can I use php and mysql in teminal
We can add php and mysql path in our path variable. The quickest way to use php and mysql in terminal is, make symbolic link
~~~
sudo ln -s /opt/lampp/bin/php /usr/bin/php
sudo ln -s /opt/lampp/bin/mysql /usr/bin/mysql
~~~
Or we can add php and mysql location to our path. I believe adding php and mysql in our path will be good idea. open `~/.bashrc` or `~/.zshrc` file and paste following code.

~~~
export PATH="/opt/lampp/bin:$PATH"
~~~


## Installing composer
In order to install composer we need to install some php extension for php. Those extension is essential for installing laravel or lot of others php package.
~~~
apt install php-mcrypt php-gd php-mbstring
~~~
Download composer.phar file from official composer website and move composer.phar file to `/usr/bin` folder with composer name by following code.
~~~
sudo mv composer.phar /usr/bin/composer
~~~
Sometime we may need to install composer global package. In this case we should add composer bin folder to our path in `~/.zshrc` or `~/.bashrc` file.
~~~
export PATH="$HOME/.config/composer/vendor/bin/:$PATH"
~~~
For tinkering laravel project we need readline in ubuntu. we can install a readline apps using following command.
~~~
sudo apt install rlwrap
~~~

By using rlwrap prefix command we can cycle through previous command in laravel tinker. For tinkering laravel in ubuntu instead of `php artisan tinker` we will use following command.
~~~
rlwrap php artisan tinker
~~~
Thats all. Hope this will you.