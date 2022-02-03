# models

### introduction

models adalah sebuah represntasi sendiri dengan database yang menghubungkan antara database dan bisnis logic query data pada pola mvc.

### writing model

ini bentuk contoh model dasar, model membutuhkan method pada class database jadi class database akan dipanggil menggunakan _`use MiniMvc\Apps\Core\Bootstraping\Database;`_

```php
use MiniMvc\Apps\Core\Bootstraping\Database;


class User_model
{
	private $table = 'tb_user';
	private $db;

	public function __construct()
	{
		$this->db = new Database;
	}

	// code here
	public function getAllUser()
	{

		$this->db->query('SELECT * FROM ' . $this->table);
		return $this->db->resultSetArray();
	}

	public function getUserId($id)
	{
		$this->db->query('SELECT * FROM ' . $this->table . ' WHERE id=:id');
		
		$this->db->bind('id', $id);
		return $this->db->singleArray();
	}

	public function deleteUserId($id)
	{
		$this->db->query('DELETE FROM ' . $this->table . ' WHERE id=:id');
		$this->db->bind('id', $id);

		$this->db->execute();
		return $this->db->rowCount();
	}

	public function getUser($username, $password)
	{

		$this->db->query('SELECT * FROM ' . $this->table . ' WHERE user_name=:user_name AND passw=:passw');

		$this->db->bind('user_name', $username);
		$this->db->bind('passw', $password);
		return $this->db->singleArray();
	}

	public function register($data)
	{
		// (`id`, `userid`, `nama`, `deskripsi`, `foto`, `user_name`, `passw`, `level`);
		$query = "INSERT INTO $this->table VALUES ('','',:nama,:deskripsi,:foto,:user_name,:passw,:level)";
		$this->db->query($query);

		// binding untuk data text
		$this->db->bind('nama', $data['nama']);
		$this->db->bind('deskripsi', $data['deskripsi']);
		$this->db->bind('user_name', $data['username']);
		$this->db->bind('passw', $data['password']);
		$this->db->bind('level', $data['status']);

		// binding untuk data file
		$this->db->bind('foto', $data['image']);

		$this->db->execute();
		return $this->db->rowCount();
	}
}
```

kamu bisa memanggil model pada controller/controller\_name.php , routes/web.php atau api/api\_name.php. dengan memanggil class

### load model pada controller

_ini metode atau cara pertama :_

```php
use MiniMvc\Apps\Core\Bootstraping\Controller;

class Welcome extends Controller
{
	public function index()
	{
		// panggil model save di variabel
		$data = $this->model("namamodel")->nama_method();
	}
}
```

_ini metode atau cara kedua :_

```php
<?php
defined('BASEURL') or exit('No direct script access allowed');

use MiniMvc\Apps\Core\Bootstraping\Controller;

class Welcome extends Controller
{

	public function index()
	{
		// panggil model
		$data = model("namamodel")->nama_method();
	}

}
```

### command shell nagara

untuk cara kedua juga bisa menggunakan command shell nagara

```php
php nagara buat:models NamaModel
```

{% hint style="danger" %}
secara default nagara akan membuat file baru di root folder models, tidak bisa nested folder
{% endhint %}

{% hint style="info" %}
nama class dibuat manual sesual nama filenya
{% endhint %}

**contoh nested folder models/admin ini tidak di support command shell nagara**

```php
php nagara buat:models NamaFolder/NamaModels
```

{% hint style="danger" %}
tidak support nested
{% endhint %}

