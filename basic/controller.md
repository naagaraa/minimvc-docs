# controller



### Introduction

controller adalah sebuah representasi yang mengolah bisinis logic sendiri yang saling terhubung dalam konsep MVC yaitu antara model dan view yang dihubungkan melalui route.

### writing controller

#### `basic controller`

ini bentuk contoh controller dasar, ingat controller extends ke class controller pada core mini mvc php.`use MiniMvc\Apps\Core\Bootstraping\Controller;`

```php
<?php
namespace app\controllers;

use MiniMvc\Apps\Core\Bootstraping\Controller;

class MainController extends Controller
{
	public function __construct()
	{
		// constructor here

	}
	public function index()
	{
		// code index here
		$data = [
			'judul' => "Example view",
			'content' => "this is content"
		];

		$this->view("nameofview", $data);
	}

	public function show($request)
	{
		// code here show here
	}

	public function create()
	{
		// code here create here
	}

	public function update($request)
	{
		// code here update here
	}

	public function remove($request)
	{
		// code here remove here
	}
}
```

untuk selanjutkan kamu perlu mendefinisikan routingnya agar controller bisa dipanggil seperti berikut pada web.php ;

```php
namespace MiniMvc\Apps\Routes\Bootstraping;

use \MiniMvc\Apps\Core\Bootstraping\Routes;
use \Bramus\Router\Router;

$router->get('example', function () {
	Routes::Routing('ExampleController', 'index');
});
```

untuk routing lebih lanjut silahkan baca [routing](broken-reference).

### command shell nagara

untuk cara kedua juga bisa menggunakan command shell nagara

```php
php nagara buat:controller NamaController
```

{% hint style="success" %}
sudah bisa nested directory
{% endhint %}

```php
php nagara buat:controller Folder/NamaController
```

```php
php nagara buat:controller Folder/Folder/NamaController
```

### passing data tke view

```php
namespace app\controllers;

use MiniMvc\Apps\Core\Bootstraping\Controller;

class BasicController extends Controller
{
	public function __construct()
	{
		// code here
	}

	public function index()
	{
		// echo "ini controller home";
		$data = [
				"title" => "homepage",
				"content" => $this->model("artikel")->getall(),
		];
		
		$this->view("home_view", $data);
	}
}
```

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic View</title>
</head>
<body>
    <h1><?= $title ?></h1>
    <main>
        <?php foreach($content as $key):?>
            <p><?php= $key->content ?></p>
        <?php endforeach;?>
    </main>
</body>
</html>
```
