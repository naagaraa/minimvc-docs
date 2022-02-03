# ML



## Introduction

oke next saya melakukan integration dengan php-ml untuk kemungkinan bila mana nanti akan berhubungan dengan ML namun dengan bahasa PHP thank to Rubix ML dan  [Andrew DalPino](https://github.com/andrewdalpino),  [Marc Laporte](https://github.com/marclaporte),  [Chris Simpson](https://github.com/simplechris), dan [Alex Torchenko](https://github.com/torchello). pengembang dari Rubix ML.

## RUBIX ML ?

_**full documentation visit**_ [_**Official**_](https://rubixml.com) _**atau**_ [_**Repository**_](https://github.com/RubixML) _****_&#x20;

" Rubix ML adalah pustaka pembelajaran mesin (ML) sumber terbuka gratis yang memungkinkan Anda membuat program yang belajar dari data Anda menggunakan bahasa PHP. Kami menyediakan alat untuk seluruh siklus hidup pembelajaran mesin dari ETL hingga pelatihan, validasi silang, dan produksi dengan lebih dari 40 algoritme pembelajaran yang diawasi dan tidak diawasi. Selain itu, kami menyediakan tutorial dan konten pendidikan lainnya untuk membantu Anda mulai menggunakan ML dalam proyek Anda. "

> intro from rubixml.com

{% hint style="info" %}
intro dari [https://rubixml.com/](https://rubixml.com)
{% endhint %}

## Basic Usage

untuk cara pemakaian example bisa check [documentation-nya](https://docs.rubixml.com/latest/installation.html#requirements) , page installation, disana ada  **Recommended** dan **** **Optional.**

untuk recoemended sudah saya pasang **Tensor Extension** untuk fast Matrix/computing dan untuk optionalnya kalian bisa baca sendiri karna tidak saya pasang untuk default pada **mini mvc php native project.**&#x20;

berikut beberapa optional :

**Optional**

* [Extras Package](https://github.com/RubixML/Extras) for experimental features
* [GD extension](https://php.net/manual/en/book.image.php) for image manipulation
* [Mbstring extension](https://www.php.net/manual/en/book.mbstring.php) for fast multibyte string manipulation
* [SVM extension](https://php.net/manual/en/book.svm.php) for Support Vector Machine engine (libsvm)
* [Redis extension](https://github.com/phpredis/phpredis) for persisting to a Redis DB

## Example

example atau contoh ini diambil dari official nya untuk cara penggunaan dan testing library tidak error ketika dipanggil.

### controller

code pada berkas controller example.php

`file example.php`

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\Controller;

// import libraries
use Rubix\ML\Datasets\Labeled;
use Rubix\ML\Classifiers\KNearestNeighbors;

class Example extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		echo "ini controller home test ML Metode KNearest Neighbors<br><br>";
		echo "Metode KNearest Neighbors<br><br>";
		$samples = [
			[3, 4, 50.5],
			[1, 5, 24.7],
			[4, 4, 62.0],
			[3, 2, 31.1],
		];
		
		$labels = ['married', 'divorced', 'married', 'divorced'];

		$dataset = new Labeled($samples, $labels);
		$estimator = new KNearestNeighbors(3);
		$estimator->train($dataset);

		echo "hasil akhir boolean = " . $estimator->trained();
		var_dump($estimator->trained()); // return true or 1
	}

}
```

### routes

atur arah routes atau patternya

`file web.php`

```php
$router->get('example-test', function () {
	Routes::Routing("Example", "index");
});
```

### hasil / result&#x20;

```php
C:\xampp\htdocs\mini-mvc-php-native\apps\controllers\Example.php:60:boolean true
```

#### Disclaimer

{% hint style="info" %}
library ini milik [RUBIXML](https://github.com/RubixML) bukan milik saya
{% endhint %}
