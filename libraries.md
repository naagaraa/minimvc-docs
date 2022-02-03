---
description: >-
  libraries adalah sebuah directory yang memungkinkan temen temen bisa membuat
  libraries atau custom helper sendiri dengan OOP format.
---

# libraries

## Introduction

by default untuk membuat libraries tidak bisa nested folder, \
example :\


* &#x20;libraries :
  * folder A :
    * Libraries\_A.php
  * &#x20;folder B:
    * Libraries\_B.php

{% hint style="danger" %}
tidak support nested folder
{% endhint %}

jadi penulisannya sturuktural foldernya adalah sebagai berikut

* &#x20;libraries :
  * Libraries\_A.php
  * Libraries\_B.php



## Basic usage

### membuat libraries

untuk membuat libraries sendiri nama file diawali dengan huruf besar atau penulisan style dengan penamaan **Pascal Case** yang tidak tau soal case style bisa baca [disini ](https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841).

```php
<?php

Namespace MiniMvc\Apps\Libraries;

class Examplelibraries 
{
    public function name(){
        echo "miyuki nagara";
    }
    
}
```

### menggunakan librariesnya

untuk menggunakannya panggil pada controllernya dan definisikan secara OOP yakni membuat object dari class tersebut.

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\Controller;
use MiniMvc\Apps\Libraries\Info_Agent;

class Example extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		// buat object dari class
		$example = new Example_libraries;
		
		// panggil method yang diinginkan
	 	$nama = $example->nama(); 
  	// cetak
    echo $nama   // return miyuki nagara
    
    // atau debug
    var_dump($nama);
	}

}
```

### command shell nagara

untuk cara kedua juga bisa menggunakan command shell nagara

```php
php nagara buat:libraries NamaLibraries
```

{% hint style="success" %}
sudah support nested directory
{% endhint %}

```php
php nagara buat:libraries Folder/NamaLibraries
```







