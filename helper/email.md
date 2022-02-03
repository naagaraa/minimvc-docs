---
description: >-
  untuk configuration email menggunakan SMPTP saya menggunakan PHP MAILER dengan
  bentuk valuenya adalah array associative
---

# email



```php
<?php
namespace app\controllers;

use app\controllers\email\mailer; #panggil class mailer
use MiniMvc\Apps\Core\Bootstraping\Controller;

class gambar extends Controller
{

	public function __construct()
	{
		// code here
	}
	
	public function confirmasi_password()
	{
		// data yang akan dikirim ke template email
		$email = [
			"to" =>"miyuki@gmail.com",
			"subject" => "confirmasi email",
			"message" => "hello worl",
			"header" => "ini headernya",
		];

		// load template emailnya dan passing datanya
		$view = mailer::confirmation($email);
		// dump($view);

		smptp_mail([
			"to" => "hello@mail.com",
			"subject" => "this is subject",
			"message" => "this is message",
			"header" => "this is header",
			"template" => $view
		]);
	}
}
```

## Style Template

{% hint style="danger" %}
ketika melakukan style, dan di template view email terdapat variabel tidak aktif, karena di kirim melalui controller yang berbeda.&#x20;
{% endhint %}

solution :

{% hint style="info" %}
commnent atau remove dulu variabel pada berkas view email tersebut
{% endhint %}

### definisikan routingnya

```php
$router->mount('/mail/message', function () use ($router) {

	// $router->set404(function () {
	// 	header('HTTP/1.1 404 Not Found');
	// 	redirect_404();
	// });

	/**
	 * return get /mail/message/confirmation
	 */
	$router->get('confirmation', function () {
		// echo "hi";
		Routes::Routing("email/mailer", "confirmation");
	});

});
```

### aktifkan view() pada method mailer.php

```php
public static function confirmation($data = [])
	{	
		// return string
		view("email.confirmation");
		// return template("confirmation", $data);
	}
```

### check melalui url untuk melihat hasilnya

```php
http://localhost/mini-mvc-php-native/mail/message/confirmation
```

