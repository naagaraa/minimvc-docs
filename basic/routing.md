---
description: untuk mengatur pattern url pada mini mvc
---

# routing

### Introduction&#x20;

routing pada konsep MVC berperan sebagai penghubung antara view dan controller.

### Basic Routing

secara default mini mvc menerapkan bramus router sebagai routing system-nya,&#x20;

```php
<?php

namespace MiniMvc\Apps\Routes\Bootstraping;

use \MiniMvc\Apps\Core\Bootstraping\Routes;
use \Bramus\Router\Router;

// Create a Router object dari bramus router
$router = new Router();

# configuruation route
$router->get('/', function () {
	return view('Welcome');
});

// run route!
$router->run();
```

### memanggil controller pada route

untuk memanggil controller pada route formatnya begini ;

jika controller tidak di dalam folder atau berada di root folder _**controller**_

```php
Routes::Routing('controller', 'method');
```

jika controller berada di dalam folder atau example _**controller/admin/AdminController.php**_

```php
Routes::Routing('folder/controller', 'method');
```

jika route memiliki slug atau parameter,

```php
Routes::Routing('folder/controller', 'method', [slug]);
```

```php
$router->get('/pathroute/{slug}', function ($slug) {
    // handle here
    Routes::Routing('folder/controller', 'method',[$slug]);
});
```

### Method Available by Bramus Route

```php
$router->get('pattern', function() { /* ... */ });
$router->post('pattern', function() { /* ... */ });
$router->put('pattern', function() { /* ... */ });
$router->delete('pattern', function() { /* ... */ });
$router->options('pattern', function() { /* ... */ });
$router->patch('pattern', function() { /* ... */ });
```

{% hint style="warning" %}
yang saya pakai hanya GET dan POST saja sisanya temen temen bisa kembangkan
{% endhint %}

### View

pada route juga bisa hanya me-return sebuah view yaitu dengan seperti ini

```php
$router->get('/', function () {
	return view('Welcome');
});
```

atau seperti ini :

```php
$router->get('/', function () {
	return view('Welcome');
	exit;
});
```

route tetaplah code programing php, jadi tetap bisa melakukan menuliskan program di dalam route seperti berikut contohnya

```php
$router->get('/', function () {
	echo "hi, my name miyuki nagara I'am a student and programmer"
	exit;
});
```

### 404 rewrite

secara default saya menyediakan 3 tampilan 404 yang bisa di custom, sesuai selera masing masing, namun untuk mengaktifkan redirect 404 yaitu dengan meng uncomment code berikut pada web.php dan untuk menoaktifkannya di comment saja.

```php
#custom 404 header un-commnet baris berikut
$router->set404(function () {
	header('HTTP/1.1 404 Not Found');
	redirect_404();
});
```

dengan uncommnet maka mode debug atau development aktif

```php
//$router->set404(function () {
//	header('HTTP/1.1 404 Not Found');
//	redirect_404();
//});
```

### warning url

{% hint style="danger" %}
beberapa pattern url yang tidak support&#x20;
{% endhint %}

* **/vendor**
* **/test**
* **/example**
* **/public**
* **/storage**
* **/system**
* **/temp**
* **/database**
* **/apps**

{% hint style="warning" %}
pattern url diatas tidak di support oleh routing
{% endhint %}

example atau contoh yang tidak di support

```php
$router->get('example', function () {
	Routes::Routing("Example", "index");
});
```

example atau contoh alternative yang di support

{% hint style="success" %}
contoh yang di support&#x20;
{% endhint %}

```php
$router->get('example-test', function () {
	Routes::Routing("Example", "index");
});
```

