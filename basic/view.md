# view



### Introduction

view merupakan tampilan pada front-end yang menangani tampilan atau bagaimana data itu ditampilkan pada halaman users pada konsep MVC

### writing view

ini bentuk contoh view dasar, catatan untuk memanggil view bisa menggunakan dua yaitu dengan code `$this->view("namaview");` dan `view("namaview");`

#### basic view

ini contoh view. _**view/home\_view.php**_

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic View</title>
</head>
<body>
    <h1>Hello World, welcome to the new world</h1>
</body>
</html>
```

untuk memanggil view pada controller metode pertama;

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
		$this->view("home_view");
	}
}
```

untuk memanggil view pada controller metode kedua&#x20;

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
		return view("home_view");
	}
}
```

### parsing data dari controller ke view

data yang di parsing dari controller ke view adalah berbentuk array assoc atau associatif yaitu key dan value. parsing data atau biasa disebut mengirim data dari controller ke view.

untuk parsing bisa menggunakan&#x20;

`$this->view("namaview", $data);`  atau `view("namaview", $data);`

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

### untuk menampilan datanya pada view

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

### parsing data ke templating atau view lain-nya

contoh  ;

```php
$data = [
    "title" => "home page",
    "bio" => [
        "nama" => "miyuki nagara ",
        "class" => "assasin"
    ]
];

view("backend.pages.home", $data);
```

lalu pada viewnya page/home :

> berkas home memanggil layout header dan footer dan pada header membutuhkan data, maka kirimkan dalam format array.

```php
<?= view("backend.layout.header", [
    "title" => $title,
    "data" => [
        "nama" => "nita",
    ]
]); ?>

<h1><?= $title ?></h1>

<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nostrum, voluptatum magni repellat nulla error, rem culpa fugit laboriosam cum ratione voluptate. Voluptatem sequi mollitia reiciendis, recusandae in illo cumque officiis.</p>

<?= view("backend.layout.footer") ?>
```

### command shell nagara

untuk cara kedua juga bisa menggunakan command shell nagara

```php
php nagara buat:view NamaView
```

{% hint style="success" %}
sudah support nested directory
{% endhint %}

```php
php nagara buat:view Folder/NamaView
```

```php
php nagara buat:view Folder/Folder/NamaView
```

### menulis php pada view

untuk menulis php pada view sama pada file php umumnya, yaitu dengan memanggil atau declarasi program php pada view, example :

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
        <?php 
        
        $data = htmlspecialcharacter($content);
        
        ?>
    </main>
</body>
</html>
```
