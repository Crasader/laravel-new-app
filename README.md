# Laravel New App - Step by Step
Pratical step-by-step how to do a new app in Laravel 5.5 and set permissions correctly on linux

### Prerequisites
* Apache
* PHP
* Composer

### Initial notes
The project in this repo is just one example of a new app build in Laravel.
If you cloned it you shouldn't run the first step.

### Step 1 - Create the project
Considering that composer is installed, run
```
composer create-project --prefer-dist laravel/laravel laravel-new-app
```

### Step 2 - Encryption key
In the project dir, generate the laravel encryption key running
```
php artisan key:generate
```

### Step 3 - Set permissions
Set 755 permission to project (laravel-new-app) dir
```
chmod -R 755 laravel-new-app
```

Set "www-data" group owner to "storage" dir and "bootstrap/cache" dir
```
chown -R :www-data laravel-new-app/storage
chown -R :www-data laravel-new-app/bootstrap/cache
```

Set 775 permission to "storage" dir and "bootstrap/cache" dir
```
chmod -R 775 laravel-new-app/storage
chmod -R 775 laravel-new-app/bootstrap/cache
```

### Step 4 - Configure database
On .env file set the database (mysql in this example)
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=mynewapp
DB_USERNAME=usermysql
DB_PASSWORD=passwordmysql
```

### Step 5 - Run migrations
To test database and create the first tables run
```
php artisan migrate
```

### Note
If any permission error appear while testing the project, repeat step 3.

## References
* [Laravel docs](https://laravel.com/docs/5.5) - Laravel Documentation
