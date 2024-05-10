# Installation procedure (manual installation)
These are the steps required to start Exment.  
※  This is a manual installation method.

## important point
- **If you do not have a web server, [set up the server](/server) first.**  
(If you do not know if you have built a server, please check it once)

- If an error occurs during installation, please refer to [Troubleshooting](/troubleshooting)

- Currently, we are unable to accept individual inquiries regarding installation procedures or server construction. If you would like individual support, please request paid support.

## composer introduction
Exment requires the introduction of composer. Please refer here for the introduction method.  
※ Those who have already introduced are unnecessary.
- [Official site](https://getcomposer.org/download/)
- [Windows version explanation site](https://weblabo.oscasierra.net/php-composer-windows-install/)
- [Linux version explanation site](https://weblabo.oscasierra.net/php-composer-centos-install/)
- [Commentary site for Mac](https://weblabo.oscasierra.net/php-composer-macos-homebrew-install/)

## Laravel installation (project creation)
- At the command line, execute the following command:  
※ The folder of the created project is called "root directory" in this manual.  

~~~
composer create-project "laravel/laravel=10.*" (Project name)
cd (Project name)
composer config --no-plugins allow-plugins.kylekatarnls/update-helper true
composer require psr/simple-cache=^2.0.0
composer require psr/http-message="1.*"
composer require nesbot/carbon=~2.71.0
composer require exceedone/exment -W
# If you want to specify the Exment version, execute the following instead. Example: v3.2.6
composer require exceedone/exment=3.2.6
# If you want to specify the Exment version, execute the following instead. Example 2: develop (development version)
composer require exceedone/exment=dev-develop
~~~

## Create database
- Create a database for Exment with MySQL.


## .env change

- Open ".env" and add or change the following contents.  
 **※Note that the value of DB_CONNECTION differs depending on whether your database is MySQL or MariaDB.**  

~~~
# Required items below --------------------
# basic setting
APP_URL=http://XXXX.com # URL to access the site. "admin" not required

# Change database settings  
# For MySQL, the following settings (default)  
DB_CONNECTION = mysql  
# In case of MariaDB, modify to the following settings  
DB_CONNECTION = mariadb  

DB_HOST=127.0.0.1 #MySQL host name
DB_PORT=3306 #MySQL port number
DB_DATABASE=homestead #MySQL database name for Exment
DB_USERNAME=homestead #MySQL database user name for Exment
DB_PASSWORD=secret # 1 password of MySQL Exment database

# Japanese and Japanese time settings from v1.2.0. Set by copy and paste
APP_TIMEZONE=Asia/Tokyo
APP_LOCALE=ja


# Optional items below --------------------

# Change the settings for sending mail. Set when sending password reset emails, etc.
MAIL_DRIVER=smtp
MAIL_HOST=smtp.mailtrap.io # Host name for mail server
MAIL_PORT=2525 #Port number for mail server
MAIL_USERNAME=null  # mail server user name
MAIL_PASSWORD=null # mail server password
MAIL_ENCRYPTION=null # Enter "ssl" when using ssl

# add for https communication
ADMIN_HTTPS=true

~~~


## Command execution
- Execute the following command.

~~~
php artisan vendor:publish --provider="Exceedone\Exment\ExmentServiceProvider"
php artisan passport:keys
php artisan exment:install
~~~

## Setting completed
After the installation is complete, continue with the [initial settings](/first_setting.md).

## Other initial settings
With the above operations, you can start Exment, but you may need to configure additional settings to use some functions.  
Please check the link below.  
- [Change / delete "admin" included in URL](/quickstart_more.md#Change/delete-"admin"-included-in-URL)
- [Task schedule function](/quickstart_more.md#Task-schedule-function)
- [Server external communication off](/quickstart_more.md#Server-external=communication-off)
- [Change file upload limit size](/quickstart_more.md#Change-file-upload-limit-size)


