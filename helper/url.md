# url

### current\_url()

current url adalah sebuah function yang di buat untuk mendapatkan url saat ini atau url yang sedang aktif. example _localhost/news/berita-saat-ini_

```php
echo current_url(); // return localhost/news/berita-saat-ini
```

### get\_url()

get\_url adalah sebuah function yang dibuat untuk mendapatkan URL berdasarkan indexnya. example :\
_localhost/news/berita-saat-ini_ maka pada indexnya path _news_ berada pada index 0.\
_localhost/0/1/2/3 ..._

```php
echo get_url(0); // return news
```

