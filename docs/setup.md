Setup Apache 2.4, PHP 5.6, MySQL, Composer
* Install PHP5 MCrypt

`# sudo apt-get install php5-mcrypt`

`# sudo php5enmod mcrypt`

`# php -i | grep mcrypt`
* Install Composer
```
# curl -sS https://getcomposer.org/installer | php
# sudo mv composer.phar /usr/local/bin/composer
```

* Create user and database:

`# mysql -uroot -pxxxxxx`

xxxxxx is password of user root;

```
CREATE USER 'fbvn'@'localhost'
    IDENTIFIED BY 'fbvn';

CREATE DATABASE fbvn_db
    DEFAULT CHARACTER SET utf8
    DEFAULT COLLATE utf8_unicode_ci;

GRANT ALL PRIVILEGES ON fbvn_db.*
    TO 'fbvn'@'localhost'
    WITH GRANT OPTION;
```

* Config dynamic virtual host

Create a folder for storing your projects alias. For example, I use `/www`. Remember to change mode it.

Add the following config to apache config file.

```
<Directory /www/>
    Options FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
 ```

 ```
<VirtualHost *:80>
    RewriteEngine On
    RewriteMap lowercase int:tolower
    RewriteCond /www/${lowercase:%{SERVER_NAME}} -d
    RewriteRule ^/(.*)$ /www/${lowercase:%{SERVER_NAME}}/$1 [L]
    <Directory />
        Require all granted
        Options FollowSymLinks Includes ExecCGI
        AllowOverride All
        Order allow,deny
        Allow from all
   </Directory>
</VirtualHost>
```

Then restart apache.

Now you can use dynamic virtual host by creating an alias in `/www` folder.

For example, we need to access this project via the address `facebookvn.com`, so create the symbolic link like this:
`ln -s /path/to/you/project/public facebookvn.com`

Finally, add `facebookvn.com` to you `hosts` file.

<code>127.0.0.1 facebookvn.com</code>

#### 2. Configure site:

Run commands on terminal

*  <code># sudo composer install</code>

*  <code># sudo composer update</code>
*  <code># sudo chmod -R 777 /path/fbvn/app/storage</code>

* Note:

If have an error: "No data received". Must to turn off XCache, make the following changes to your PHP configuration:

`# sudo vim /etc/php5/mods-available/xcache.ini`

Change to:

```
xcache.cacher Off
xcache.size 0
xcache.stat Off
```

#### 2. Migrate Database:
* Running All Outstanding Migrations

```
php artisan migrate
```

* Rollback all migrations and run them all again

```
php artisan migrate:refresh --seed
```

#### 3. Go to URL:
http://facebookvn.com/

