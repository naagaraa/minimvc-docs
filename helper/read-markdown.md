# read markdown

## markdown file

update function baru untuk membaca file markdown dan melakukan convert ke HTML, function ini dibuat untuk tujuan membaca markdown files, terlebih lagi untuk dalam pembuatan documentation program.

### path

base path untuk markdown files terletak pada directory **views/markdown**

### basic usage

```php
<?php
// call function
read_markdown("name of markdown file withoud extention");

// example
// read file example.md
read_markdown("example");

```

### basic usage with controller and view

untuk menggunakan bersama controller dan view

1. buat controller
2. buat template views pada directory views
3. buat file .md atau pada directory markdown

#### controller

contoh file controller

```php
<?php
namespace app\controllers;

use MiniMvc\Apps\Core\Bootstraping\Controller;
use MiniMvc\Apps\Core\Bootstraping\Request;
use app\controllers\email\mailer;
use MiniMVC\System\Storage;

class welcome extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		//echo "controller welcome method index";
		$data  = [
			"title" => "read markdown files",
			"markdown_content" => read_markdown("example")
		];

		view("example_v", $data);
	}

}

```

#### view

contoh file views

```php
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- show title -->
    <title><?= $title ?></title>
</head>

<body>
    <!-- show markdown file -->
    <?= $markdown_content ?>
</body>

</html>
```

#### markdown

contoh file markdown

```markdown
### this is example

<p>markdown file basic</p>

```

#### route

contoh arah route

```php
//  default welcome
$router->get('/', function () {
    // return view('Welcome'); # langsung view
    Routes::Routing("welcome", "index"); # panggil controller
});

```





