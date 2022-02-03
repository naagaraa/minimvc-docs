# asset



### asset()

asset() adalah function yang dibuat untuk mendapatkan root folder asset yaitu public

example untuk memanggil file css

```php
<?=  asset("css/style.css"); ?>  // return domainname/public/css/style.css
```

example untuk memanggil fille js

```php
<?= asset("js/main.jd"); ?>  // return domainname/public/js/main.js
```

example untuk memanggil file image

```php
<?=  asset("img/banner.jpg"); ?>  // return domainname/public/img/banner.jpg
```

### storage()

storage() adalah function yang dibuat untuk mendapatkan root folder storage yaitu storage. storage adalah tempat penyimpanan khusus seperti gambar, document dll.

example

```php
<?=  asset("img/banner.jpg"); ?>  // return domainname/storage/img/banner.jpg
```

pada html\_view.php :

```php
<img src="<?=  asset("img/banner.jpg"); ?>" alt="gambar">
```

### temp\_dir()

temp_dir() adalah function yang dibuat untuk mendapatkan root_ folder temp __ dir yaitu temp. temp adalah tempat penyimpanan sementara.

```php
<?= asset("gambar.jpg"); ?>  // return domainname/temp/gambar.jpg
```
