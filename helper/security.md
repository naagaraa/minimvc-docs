# Security



## XSS Prevent

**XSS** merupakan kependekan yang digunakan untuk istilah **cross site scripting**. **XSS** merupakan salah satu jenis serangan injeksi code (code injection attack). **XSS** dilakukan oleh penyerang dengan cara memasukkan kode HTML atau client script code lainnya ke suatu situs.

```php
// basic
Security::xss($content)

// no aktif
Security::xss($content, 0)
```

### basic usage

#### controller

```php
class welcome extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		// echo "controller welcome method index";
		// echo $data;
		$data  = [
			"title" => "read markdown files",
			"content" => "content here"
		];

		view("example_v", $data);
	}

	public function about()
	{
		echo "controller about";
	}
}
```



#### view

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
    <?= Security::xss($content); ?>
</body>

</html>
```
