---
description: agent adalah helper yang menampilkan info pada client
---

# agent

### Introduction

info agent adalah sebuah helper yang saya letakan pada directory libraries, Agent digunakan biasanya untuk mendapatkan info browser tang digunakan client, misalnya seperti

1. sistem operasi atau OS
2. type Browser
3. Ip client
4. ip server

### Basic usage

untuk cara penggunakan simple saja karna ini OOP. pada controller

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\Controller;

// import class
use MiniMvc\Apps\Libraries\Agent;

class Example extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		// buat object dari class
		$info_agent = new Agent;
		
		// panggil method yang diinginkan
	 	$os = $info_agent::get_os();
 		$browser = $info_agent::get_browser();
 		$ip_client = $info_agent::get_ip_client();
 		$ip_server = $info_agent::get_ip_server();
 
		// cetak
		// echo $os;
		
		// atau debug
		var_dump($os);				// return windows 10 / sistem operasi
		var_dump($browser);			// return chrome / browser
		var_dump($ip_client);		// return ip ::1 atau 127.0.0.1 atau ip client
		var_dump($ip_server);		// return ip server

		// atau begini tampa create object

		var_dump(Agent::get_os());
		var_dump(Agent::get_browser());
		var_dump(Agent::get_ip_client());
		var_dump(Agent::get_ip_server());
	}

}
```

{% hint style="info" %}
hanya terdapat 4 method untuk info agent
{% endhint %}

### Tabel Info <a href="#tabel-info" id="tabel-info"></a>

