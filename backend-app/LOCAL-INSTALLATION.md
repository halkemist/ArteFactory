# App Local Installation

## Requirements

- Apache
- MySQL
- PHP
- Composer

### LAMP server (PHP, Apache, MySQL)

If you didn't have the requirements, you can install LAMP server:

```bash
$ sudo apt install lamp-server^
$ sudo service apache2 start 
```

Now you have /var/www/html/ server directory, put the project inside.

### Update packages

```bash
$ composer install
```

### MySQL

Check the DB_USERNAME, DB_DATABASE and DB_PASSWORD from .env file, create the user, the DB and grant privileges to the user.

```bash
$ sudo mysql
> CREATE USER 'DB_USERNAME'@'localhost' IDENTIFIED BY 'DB_PASSWORD';
> GRANT ALL PRIVILEGES ON DB_NAME.* TO 'DB_USERNAME'@'localhost';
> FLUSH PRIVILEGES;
> EXIT;
```

```bash
$ sudo mysql
> CREATE DATABASE DB_DATABASE;
> EXIT;

### Project database migration

```bash
$ php artisan migrate
```

