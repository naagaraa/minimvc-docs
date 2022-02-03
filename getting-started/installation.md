---
description: user guide untuk installation
---

# Installation



```bash
code .
```

{% hint style="info" %}
jika package error lakukan composer update
{% endhint %}

atau bisa lihat cara installnya pada playlist berikut ini

* [mini mvc](https://www.youtube.com/playlist?list=PLK5\_CL-hAKCf-H7snj3RlLVjrkJ7yql6o)

### install diluar htdocs

jika menggunakan windows dan menggunakan xampp sebagai build in servernya maka sebagai berikut cara installnya. **open terminal** atau **command promt** untuk navigasinya



open terminal atau command promt ( contoh )

```bash
PS D:\CodingDev\php>
```

install project melalaui composer

```bash
composer create-project nagara/mini-mvc-php-native belajarmvc
```

{% hint style="info" %}
alternative : composer install --prefer-source --no-interaction --no-dev -o
{% endhint %}

github update policy tentang api ketika intragte dengan composer ada masalah saat install github limit hit api default 60 hit / hours / #CMIIW

> "composer asking oauth token for download public repo or API rate limit, check this for solve problem [https://stackoverflow.com/questions/49518579/composer-asking-oauth-token-for-download-public-repo](https://stackoverflow.com/questions/49518579/composer-asking-oauth-token-for-download-public-repo) "

```bash
cd belajarmvc
```

```bash
code .
```

{% hint style="info" %}
jika package error lakukan composer update
{% endhint %}

ganti mode APP\_ENV ke development

```bash
APP_DEBUG=true
APP_ENV=development
```

jalankan build in servernya klo pake vscode bisa langsung buka command di dalamnya

```bash
php nagara server:aktif
```

maka akan berjalan di port **127.0.0.1:9000** buka pada browser atau copy saja alamatnya.
