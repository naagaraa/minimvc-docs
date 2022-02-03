# upload files



## Image Upload

{% hint style="info" %}
sedang dalam uji coba
{% endhint %}

image Upload adalah sebuah class helper dengan object oriented atau OOP yang menangani fitur image uploaded&#x20;

{% hint style="success" %}
support extention file pdf, png, jpeg, png, gif, svg, doc, docx, txt,
{% endhint %}

### upload()

uploaded memiliki 3 paramter wajib, namafile, target directory, generate name files, dan akan result sebuah data object.

```php
Upload("name_files_image", "directory", "generate_file_name");
```

### value

* "gambar" => name file dari name di html
* $directory => target directory
* false => file tidak di generate nama filesnya
* true => false di generate random nama filesnya

{% hint style="info" %}
nama "gambar nama file pada html input type files
{% endhint %}

**pada berkas view html**

```php
 <form action="<?= url("gambar/upload") ?>" method="post" enctype="multipart/form-data">
   <input type="file" name="gambar"> 
   <button type="submit">save</button>
 </form>
```

**pada berkas controller**

```php
<?php
# import class pada controller
use MiniMVC\System\Storage;

# buat object
$storage =  new Storage();

# target directory
$directory = "temp/;

# call functionnya
$data = $storage->Upload("gambar", $directory, false);

# result
var_dump($data);
```

**result berupa object**

```php
object(stdClass)[57]
    public 'image_original_name' => string 'preview.jpg' (length=11)
    public 'image_name' => string '86e8985aa845f5a82b2b72e2b7bed713.jpg' (length=36)
    public 'image_type' => string 'image/jpeg' (length=10)
    public 'image_size' => int 1238922
    public 'image_error' => int 0
```

### update files ()

untuk melakukan update files, files yang di update akan menghapus file lama dan mereplacenya dengan files baru mempunyai empat parameter

```php
UpdateFile("file_lama", "file_baru", "directory", "generate_file_name");
```

**pada berkas view html**

```php
 <form action="<?= url("gambar/update") ?>" method="post" enctype="multipart/form-data">
   <input type="file" name="gambar"> 
   <button type="submit">save</button>
 </form>
```

**pada berkas controller**

```php
<?php
use MiniMVC\System\Storage;

# buat object
$storage =  new Storage();

# target directory
$directory = temp_dir();

# call functionnya
# $oldfiles = $directory . "namafilesnya";

#example 
$oldfiles = $directory . "deecbcc27b035a55cc5692326d24e09e.png";

$data = $storage->UpdateFile($oldfiles, "gambar", $directory, true);

# result object
var_dump($data);

# get nama files
echo $data->image_name; #or

# save nama files to variabel
$image = $data->image_name;
```

### interacting image with database

untuk interacsi dengan data didatabase

```php
# uploaded algorithm

# uploade image
# 1. uploaded files images
# 2. getting name files image
# 3. insert name files image to database


# update images
# 1. update files image
# 2. getting name files image
# 3. update name files image to database
```

## Files Upload ( pdf , exel, doc )

{% hint style="info" %}
sedang dalam uji coba
{% endhint %}

### upload csv or excel

untuk upload files berformas csv atau excel dapat menggunakan libraries office yang dibuat yaitu **read\_file**_**\_**_**csv().** untuk mengubah field pada csv menjadi array. setelah berubah menjadi array bisa di coba melakukan looping insert data. ****&#x20;

```php
use MiniMvc\Apps\Libraries\office; // libraries

$office = new office;    // buat object baru
$office->read_file_csv("namefile"); // return object
```

#### example

arah routenya web.php

**web.php**

```php
$router->get('office/upload', function () {
	Routes::Routing("officeController", "index");
});
$router->post('office/upload', function () {
	Routes::Routing("officeController", "upload");
});
```

**office\_view.php**

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="office/upload" method="post" enctype="multipart/form-data" >
        <input type="file" name="document" id="document">
        <button type="submit">import</button>
    </form> 
</body>
</html>
```

pada berkas controllernya

**officeController.php**

**ini akan me return atau mengembalikan nilai array**

```php
use MiniMvc\Apps\Libraries\office;

class welcome extends Controller
{

	public function __construct()
	{
		// code here
	}

	public function index()
	{
		view("office_view");
	}

	public function upload()
	{
		$office = new office;
		$data = $office->read_file_csv("document"); // name di input html
		
		dump($data); // debug return object
	}

}
```

## Multiple Insert

untuk multiple insert data, hasil membaca file dari file excel itu bisa dilakukan dengan looping

example hasil read file excel \*covid-19 data example\*,&#x20;

{% hint style="info" %}
index 0 atau pertama adalah nama column by row,&#x20;
{% endhint %}

sebelum di remove index 0 atau nama columnnya :

```php
^ array:15 [▼
  0 => array:6 [▼
    0 => null
    1 => "ODP"
    2 => "PDP"
    3 => "POSITIF"
    4 => "SEMBUH"
    5 => "MENINGGAL"
  ]
  1 => array:6 [▼
    0 => "3/26/2020"
    1 => 204
    2 => 89
    3 => 17
    4 => 0
    5 => 4
  ]
  2 => array:6 [▶]
  3 => array:6 [▶]
  4 => array:6 [▶]
  5 => array:6 [▶]
  6 => array:6 [▶]
  7 => array:6 [▶]
  8 => array:6 [▶]
  9 => array:6 [▶]
  10 => array:6 [▶]
  11 => array:6 [▶]
  12 => array:6 [▶]
  13 => array:6 [▶]
  14 => array:6 [▶]
]
```

{% hint style="info" %}
index 1 \~ n ke dua adalah isi dari field column by row
{% endhint %}

sesudah di remove index 0 dan yg tersisa hanya isi by row

```php
^ array:14 [▼
  1 => array:6 [▼
    0 => "3/26/2020"
    1 => 204
    2 => 89
    3 => 17
    4 => 0
    5 => 4
  ]
  2 => array:6 [▼
    0 => "3/27/2020"
    1 => 207
    2 => 99
    3 => 17
    4 => 0
    5 => 4
  ]
  3 => array:6 [▶]
  4 => array:6 [▶]
  5 => array:6 [▶]
  6 => array:6 [▶]
  7 => array:6 [▶]
  8 => array:6 [▶]
  9 => array:6 [▶]
  10 => array:6 [▶]
  11 => array:6 [▶]
  12 => array:6 [▶]
  13 => array:6 [▶]
  14 => array:6 [▶]
]
```

step by step

1. remove atau unset column pada index 0
2. buat model dan method save atau insert
3. loop data readfile remove fieldnya

### buat model&#x20;

```php
class DocumentModel
{
	private $table = 'documents';
	private $db;

	public function __construct()
	{
		$this->db = new Database;
	}
	
public function save($tanggal, $odp, $pdp, $positif, $sembuh, $meninggal)
	{

    // query data insert
		// (`id`, `tanggal`, `odp`, `pdp`, `positif`, `sembuh`, `meninggal`);
		$query = "INSERT INTO $this->table VALUES ('',:tanggal,:odp,:pdp,:positif,:sembuh,:meninggal)";
		$this->db->query($query);

		// binding untuk data string
		$this->db->bind('tanggal', $tanggal);
		$this->db->bind('odp', $odp);
		$this->db->bind('pdp', $pdp);
		$this->db->bind('positif', $positif);
		$this->db->bind('sembuh', $sembuh);
		$this->db->bind('meninggal', $meninggal);

    // execute insert atau save data
		$this->db->execute();
		return $this->db->rowCount();
	}
}
```

### pada controllernya

```php
public function store()
	{
		// code here store here
		$file_excel = office::read_file_csv("files");

		// remove column
		unset($file_excel->worksheet[0]);

		// call model
		$excel = model("DocumentModel");

		// loop mutiple insert
		foreach($file_excel->worksheet as $key){
			$excel->save($key[0],$key[1],$key[2],$key[3],$key[4],$key[5]);
		}
		
	}
```
