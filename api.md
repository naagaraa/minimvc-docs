# API



### Introduction

ini tidak berbeda jauh bebeda dengan routing web.php hanya saja saya pisahkan untuk membuatnya moun kedalam group API jadi arah urlnya menjadi _domain/api/pattern_ untuk akses API.

untuk membuat API atau hanya bermain di data saja saya membuatnya pada folder apps/api yang dimana akan di handling oleh corenya yaitu API\_Handling

### Basic usage

untuk membuat API definisinan routenya pada api.php

#### api.php

```php
$router->get('/users', function () {
    API_Handling::Routing('api_management_user', 'index');
});
```

maka untuk full codenya akan terlihat seperti ini

```php
<?php

use MiniMvc\Apps\Core\Bootstraping\API_Handling;
use \Bramus\Router\Router;

// Create a Router object
$router = new Router();

$router->mount('/api', function () use ($router) {
    
    $router->set404(function () {
		    header('HTTP/1.1 404 Not Found');
		    redirect_404();
	  });
	
    // pattern
    $router->get('/users', function () {
        API_Handling::Routing('api_management_user', 'index');
    });
    
    
});


// run route!
$router->run();
```

### api\_management\_user.php

lalu pada berkasi api\__management\__user.php

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\API_Handling;

class api_management_user extends API_Handling
{
	public function __construct()
	{
		// code here
	}

    // example Api 
	public function index()
	{
		// code here dalam array assoc example
        $data = [
            'id' => 1,
            'nama' => 'ekajayanagara',
            'jobs' => [
                'freelancer illustrattor',
                'junior dev',
                'student collegue'
            ],
            'status learning' => 'Learn in Internet',
            'hobby' => 'ngulik in bahasa sunda',
            'address' => 'indonesia',
            'city' => 'jakarta',
        ];

        echo json_encode($data, JSON_PRETTY_PRINT);
	}

}
```

### Example

untuk contoh lainnya adalah sebagai berikut ini.

{% hint style="success" %}
menggunakan real data api public (lokasi indonesia)
{% endhint %}

#### api\_lokasi\_indonesia.php

berikut adalah contoh penulisan untuk get endpoint public api dari **faritdotid.com** untuk contoh **hit API** dengan bentuk JSON

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\API_Handling;

class api_lokasi_indonesia extends API_Handling
{
	public function __construct()
	{
		// code here
	}

    // example Api 
	public function index()
	{
        $url = "https://dev.farizdotid.com/api/daerahindonesia/provinsi";
        echo get_rest_api($url);
	}
}
```

### api.php

```php
<?php

use MiniMvc\Apps\Core\Bootstraping\API_Handling;
use \Bramus\Router\Router;

// Create a Router object
$router = new Router();

$router->mount('/api', function () use ($router) {
    
    $router->set404(function () {
		    header('HTTP/1.1 404 Not Found');
		    redirect_404();
	  });
	
    // pattern
    $router->get('/daerah-indonesia', function () {
        API_Handling::Routing('api_lokasi_indonesia', 'index');
    });
    
    
});


// run route!
$router->run();
```

### Hasil

melihat hasilnya pada browser _`domainname/api/daerah-indonesia`_

untuk hasilnya akan berupa data dalam bentuk JSON format seperti berikut ini.

```javascript
{
provinsi: [
        {
            id: 11,
            nama: "Aceh"
        },
        {
            id: 12,
            nama: "Sumatera Utara"
        },
        {
            id: 13,
            nama: "Sumatera Barat"
        },
        {
            id: 14,
            nama: "Riau"
        },
        {
            id: 15,
            nama: "Jambi"
        },
        {
            id: 16,
            nama: "Sumatera Selatan"
        },
        {
            id: 17,
            nama: "Bengkulu"
        },
        {
            id: 18,
            nama: "Lampung"
        },
        {
            id: 19,
            nama: "Kepulauan Bangka Belitung"
        },
        {
            id: 21,
            nama: "Kepulauan Riau"
        },
        {
            id: 31,
            nama: "Dki Jakarta"
        },
        {
            id: 32,
            nama: "Jawa Barat"
        },
        {
            id: 33,
            nama: "Jawa Tengah"
        },
        {
            id: 34,
            nama: "Di Yogyakarta"
        },
        {
            id: 35,
            nama: "Jawa Timur"
        },
        {
            id: 36,
            nama: "Banten"
        },
        {
            id: 51,
            nama: "Bali"
        },
        {
            id: 52,
            nama: "Nusa Tenggara Barat"
        },
        {
            id: 53,
            nama: "Nusa Tenggara Timur"
        },
        {
            id: 61,
            nama: "Kalimantan Barat"
        },
        {
            id: 62,
            nama: "Kalimantan Tengah"
        },
        {
            id: 63,
            nama: "Kalimantan Selatan"
        },
        {
            id: 64,
            nama: "Kalimantan Timur"
        },
        {
            id: 65,
            nama: "Kalimantan Utara"
        },
        {
            id: 71,
            nama: "Sulawesi Utara"
        },
        {
            id: 72,
            nama: "Sulawesi Tengah"
        },
        {
            id: 73,
            nama: "Sulawesi Selatan"
        },
        {
            id: 74,
            nama: "Sulawesi Tenggara"
        },
        {
            id: 75,
            nama: "Gorontalo"
        },
        {
            id: 76,
            nama: "Sulawesi Barat"
        },
        {
            id: 81,
            nama: "Maluku"
        },
        {
            id: 82,
            nama: "Maluku Utara"
        },
        {
            id: 91,
            nama: "Papua Barat"
        },
        {
            id: 94,
            nama: "Papua"
        }
    ]
}
```
