---
description: waktu atau timezone
---

# waktu



### Introduction

by default membuat function waktu untuk mendapatkan waktu saat ini, pada config/timezone.php

{% hint style="info" %}
hanya terdapat 4 function tentang timezone
{% endhint %}

### Tabel Info

| method      | keterangan                                  |
| ----------- | ------------------------------------------- |
| time\_now() | menampilakn waktu saat ini ex : 12:26:17    |
| time\_wib() | menampilkan waktu saat ini ex : 12:26:17 pm |
| date\_now() | menampilkan tanggal ex : 2021-04-15         |
| year\_now() | menampilkan tahun ex: 2021                  |

### Basic Usage

untuk menggunakan sederhana saja setiap function akan return sebuah string jadi cukup panggil saja nama functionnya pada controller atau view.

```php
<?php
time_now(); // menampilkan waktu saat ini
```
