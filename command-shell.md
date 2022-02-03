---
description: >-
  command shell adalah sebuah perintah pada terminal yang membantu dalam
  development
---

# command shell



### NAGARA

yeah, nagara the last my name, atau nama akhir saya. nama itu saya jadikan nama untuk sebuah perintah command, beberapa perintah commnad nagara yang tersedia saat ini.

{% hint style="info" %}
nagara name of creator
{% endhint %}

### List Command Available

| command                                      | keterangan                                |
| -------------------------------------------- | ----------------------------------------- |
| php nagara server:aktif                      | run server di 127.0.0.1:900               |
| php nagara generate:env                      | membuat file env sesuai nama project      |
| php nagara generate:copyenv                  | melakukan copy file env dari env.example  |
| php nagara buat:controller \<controllername> | membuat controller baru                   |
| php nagara buat:models \<modelname>          | membuat model baru                        |
| php nagara buat:views \<viewsname>           | membuat view baru                         |
| php nagara test:myname \<yourname>           | menampilkan  test name                    |
| php nagara migrate:help                      |                                           |
| php nagara migrate:rollback                  |                                           |
| php nagara migrate:run                       |                                           |
| php nagara migrate:seed                      |                                           |
| php nagara migrate:seedrun                   |                                           |
| php nagara test:bootstrap                    | untuk buat bootsrap unit testing template |
| php nagara test:build                        | untuk test build unit testing             |
| php nagara test:cest                         | untuk test cest unit testing              |
| php nagara test:run                          | untuk test run                            |
| php nagara clear-cache                       | melakukan clear-cache                     |
| php nagara help                              | menampilkan bantuan                       |
| php nagara about:author                      | menampilkan about author                  |
| php nagara about:deskription                 | menampilkan about deskription             |
| php nagara -v                                | menampilkan versi shell mini mvc saat ini |

{% hint style="warning" %}
php nagara server:aktif harus di set APP\_ENV = development
{% endhint %}

## Development mode ( build in server )

pada development mode, memungkinkan untuk meletakan berkas project tidak pada `xampp/htdocs/namaproject` namun bisa di letakan di tempat lain, misalnya, seperti `D:latihan-coding/php/namaproject.`

untuk melakukan php nagara server:aktif harus melakukan configurasi berikut pada file .env

```
APP_DEBUG=true
APP_ENV=development
```

{% hint style="info" %}
dengan syarat envirotment variabel php sudah di set
{% endhint %}

jika envirotment variabelnya sudah di set maka bisa di test untuk check versi php, ini untuk memastikan saja bahwa php shellnya bekerja.

```
php --version
```

maka hasilnya seharusnya tampil versinya kurang begini :

```
PHP 7.4.18 (cli) (built: Apr 27 2021 17:17:20) ( ZTS Visual C++ 2017 x64 )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Xdebug v3.0.4, Copyright (c) 2002-2021, by Derick Rethans
```

setelah itu baru run servernya&#x20;

```
php nagara server:aktif
```

## Local mode ( tampa build in server )

jika kamu gak mau repot harus running php nagara server:aktif maka ubah modenya jadi local mode, dan berkas project wajib diletakan pada server, bila menggunakan xampp pada windows bisa letakan pada `xampp/htdocs/namaproject`

dan seeting configuration envnya menjadi local

```
APP_DEBUG=true
APP_ENV=local
```
