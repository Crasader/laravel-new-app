# Laravel New App - Step by Step
Pratical step-by-step how to do a new app in Laravel 5.5 and set permissions correctly on linux

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
chmod -R 775 laravel-new-app/cache
```

### Step 4 - Migrations (optional)
Run the initial migrations in the project dir
```
php artisan migrate
```

### Note
If any permission error appear while test the project, repeat step 3

## References
* [Laravel docs](https://laravel.com/docs/5.5) - Laravel Documentation
