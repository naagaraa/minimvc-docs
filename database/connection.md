# connection



### connection database

secara default mini mvc menggunakan .env sebagai file configuration untuk menghindari banyak hardcode. .env adalah sebuah configurasi envirotment one to all. secara default database yang disupport baru _**mysql dan mysqli.**_

example .env configurasi :

```
# config file .env untuk configurasi pada file

APP_DEBUG=true
APP_ENV=local

# configurasi Path here
APP_NAME=mini-mvc-php-native
APP_HOST=http://localhost/

# configurasi Database here
DB_HOST=localhost
DB_PORT=3306
DB_NAME=CodeZeroDB
DB_USERNAME=root
DB_PASSWORD=
    
# configurasi mailer (on development)
MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS=null
MAIL_FROM_NAME="${APP_NAME}" 


# configurasi oAuth (on development)
CLIENT_ID=
SECRET_ID=
```

#### keterangan :

* DB\_HOST : untuk configurasi host pada database
* DB\_PORT : untuk configurasi port pada database
* DB\_NAME : untuk configrurasi database name
* DB\_USERNAME : untuk configurasi username pada database
* DB\_PASSWORD : untuk configurasi database password

```
# configurasi Database here
DB_HOST=http://localhost/
DB_PORT=3306
DB_NAME=CodeZeroDB
DB_USERNAME=root
DB_PASSWORD=
```

### Migration database

untuk melakukan migration atau menggunakan fiture migration harus melakukan configurasi di berkas apps/config/migrations.php

```php
$migration = 
[
    'paths' => [
        'migrations' => './database/migrations',
        'seeds' => './database/seeds'
    ],
    'environments' => [
        'default_migration_table' => 'mini-mvc',
        'default_environment' => 'testing',
        'production' => [
            'adapter' => 'mysql',
            'host' => 'localhost',
            'name' => 'production_db',
            'user' => 'root',
            'pass' => '',
            'port' => '3306',
            'charset' => 'utf8',
        ],
        'development' => [
            'adapter' => 'mysql',
            'host' => 'localhost',
            'name' => 'development_db',
            'user' => 'root',
            'pass' => '',
            'port' => '3306',
            'charset' => 'utf8',
        ],
        'testing' => [
            'adapter' => 'mysql',
            'host' => 'localhost',
            'name' => 'testing_db',
            'user' => 'root',
            'pass' => '',
            'port' => '3306',
            'charset' => 'utf8',
        ]
    ],
    'version_order' => 'creation'
];

```

```php
// sesuaikan dengan config .env

'default_environment' => 'testing',

'testing' => [
    'adapter' => 'mysql',
    'host' => 'localhost',
    'name' => 'testing_db',  // nama database 
    'user' => 'root',        // username database
    'pass' => '',            // password database
    'port' => '3306',
    'charset' => 'utf8',
]


```
