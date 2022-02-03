# mathecmatic

## Introduction

hi, new update, saya menambahkan library php-math untuk keperluan programing mathematic pada php bila itu diperlukan , libraries ini dibuat oleh [Mark Rogoyski](https://github.com/markrogoyski) . thx to brother.  php-math merupakan powerfull modern library math untuk php



#### Disclaimer

{% hint style="info" %}
library ini milik [Mark Rogoyski](https://github.com/markrogoyski/math-php) bukan milik saya
{% endhint %}

## Features

* [Algebra](https://github.com/markrogoyski/math-php#algebra)
* [Arithmetic](https://github.com/markrogoyski/math-php#arithmetic)
* [Finance](https://github.com/markrogoyski/math-php#finance)
* Functions
  * [Map](https://github.com/markrogoyski/math-php#functions---map---single-array)
  * [Polynomial](https://github.com/markrogoyski/math-php#functions---polynomial)
  * [Special Functions](https://github.com/markrogoyski/math-php#functions---special-functions)
* Information Theory
  * [Entropy](https://github.com/markrogoyski/math-php#information-theory---entropy)
* Linear Algebra
  * [Matrix](https://github.com/markrogoyski/math-php#linear-algebra---matrix)
  * [Vector](https://github.com/markrogoyski/math-php#linear-algebra---vector)
* Numbers
  * [Arbitrary Integer](https://github.com/markrogoyski/math-php#number---arbitrary-length-integers)
  * [Complex](https://github.com/markrogoyski/math-php#number---complex-numbers)
  * [Rational](https://github.com/markrogoyski/math-php#number---rational-numbers)
* Number Theory
  * [Integers](https://github.com/markrogoyski/math-php#number-theory---integers)
* Numerical Analysis
  * [Interpolation](https://github.com/markrogoyski/math-php#numerical-analysis---interpolation)
  * [Numerical Differentiation](https://github.com/markrogoyski/math-php#numerical-analysis---numerical-differentiation)
  * [Numerical Integration](https://github.com/markrogoyski/math-php#numerical-analysis---numerical-integration)
  * [Root Finding](https://github.com/markrogoyski/math-php#numerical-analysis---root-finding)
* Probability
  * [Combinatorics](https://github.com/markrogoyski/math-php#probability---combinatorics)
  * Distributions
    * [Continuous](https://github.com/markrogoyski/math-php#probability---continuous-distributions)
    * [Discrete](https://github.com/markrogoyski/math-php#probability---discrete-distributions)
    * [Multivariate](https://github.com/markrogoyski/math-php#probability---multivariate-distributions)
    * [Tables](https://github.com/markrogoyski/math-php#probability---distribution-tables)
* [Sample Data](https://github.com/markrogoyski/math-php#sample-data)
* [Search](https://github.com/markrogoyski/math-php#search)
* Sequences
  * [Basic](https://github.com/markrogoyski/math-php#sequences---basic)
  * [Advanced](https://github.com/markrogoyski/math-php#sequences---advanced)
  * [NonInteger](https://github.com/markrogoyski/math-php#sequences---non-integer)
* [Set Theory](https://github.com/markrogoyski/math-php#set-theory)
* Statistics
  * [ANOVA](https://github.com/markrogoyski/math-php#statistics---anova)
  * [Averages](https://github.com/markrogoyski/math-php#statistics---averages)
  * [Circular](https://github.com/markrogoyski/math-php#statistics---circular)
  * [Correlation](https://github.com/markrogoyski/math-php#statistics---correlation)
  * [Descriptive](https://github.com/markrogoyski/math-php#statistics---descriptive)
  * [Distance](https://github.com/markrogoyski/math-php#statistics---distance)
  * [Distributions](https://github.com/markrogoyski/math-php#statistics---distributions)
  * [Divergence](https://github.com/markrogoyski/math-php#statistics---divergence)
  * [Effect Size](https://github.com/markrogoyski/math-php#statistics---effect-size)
  * [Experiments](https://github.com/markrogoyski/math-php#statistics---experiments)
  * [Kernel Density Estimation](https://github.com/markrogoyski/math-php#statistics---kernel-density-estimation)
  * Multivariate
    * [PCA (Principal Component Analysis)](https://github.com/markrogoyski/math-php#statistics---multivariate---principal-component-analysis)
  * [Outlier](https://github.com/markrogoyski/math-php#statistics---outlier)
  * [Random Variables](https://github.com/markrogoyski/math-php#statistics---random-variables)
  * [Regressions](https://github.com/markrogoyski/math-php#statistics---regressions)
  * [Significance Testing](https://github.com/markrogoyski/math-php#statistics---significance-testing)
* [Trigonometry](https://github.com/markrogoyski/math-php#trigonometry)



## Documentation

untuk documentation silahkan kunjungin officialnya untuk cara penggunaannya&#x20;

### [Documentation](https://github.com/markrogoyski/math-php) official&#x20;

### github readme



## Basic usage

untuk contoh penggunaan libraries php-math pada mini mvc saya adalah sebagai berikut :&#x20;

#### controller

buat controller baru dengan nama Example.php

`file Example.php`

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\Controller;

// import libraries
use MathPHP\NumberTheory\Integer;

class Example extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		echo "ini controller home test Mathecmatic<br><br>";
		
		$n = 225;
		
		// Even and odd
		// $bool = Integer::isEven($n);
		$bool = Integer::isOdd($n);
		
		echo $bool; // atau gunakan var_dump() untuk print debug
		var_dump($bool);  //return true
		
		
	}

}
```

#### routes

atur arah route atau patternnya

`file web.php`

```php
$router->get('example-test', function () {
	Routes::Routing("Example", "index");
});
```

### Hasil

```php
C:\xampp\htdocs\mini-mvc-php-native\apps\controllers\Example.php:60:boolean true
```





