---
description: >-
  by default untuk query builder ini menggunakan PHP native namun dengan konsep
  PDO php data object jadi bukan mysql connection melainkan PDO
---

# query builder



## Introduction

untuk melakukan query sama seperti sintax SQL pada umumnya seperti SELECT, UPDATE dan lain lain untuk saat ini belum ada function khusus yang saya buat untuk menanganin database.

{% hint style="success" %}
query menggunakan PDO atau PHP data object.
{% endhint %}

## Models

pada models deklarasi configurasi berikut untuk interaksi dengan tabel yang ada pada database.

```php
class MainModel
{
	private $table = 'tb_name';  // nama tabel
	private $db;

	public function __construct()
	{
		$this->db = new Database; // buat object dabase
	}
	
	#functioon query lainnya
	public function getall(){
		# code 
	}
}
```

{% hint style="info" %}
query database dilakukan manual tidak ada function khusus
{% endhint %}

## Selecting Data

```php
$this->db->query('SELECT * FROM ' . $this->table);
return $this->db->resultSetArray();
```

## Looking Spesific Data

```php
$this->db->query('SELECT * FROM ' . $this->table . ' WHERE id=:id');
		
$this->db->bind('id', $id);
return $this->db->singleArray();
```

## Insert Data

```php
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

// execute perintahnya
$this->db->execute();
return $this->db->rowCount();   //return number

```

## Update Data

```php
// lakukan query
$query = "UPDATE " . $this->table . " SET id=:id, uniqid=:uniqid, urlid=:urlid, judul_content=:judul_content, visit_views=:visit_views, visitor_ip=:visitor_ip, waktu=:waktu WHERE uniqid=:uniqid";
$this->db->query($query);

// binding untuk data text
$this->db->bind('id', $data['id']);
$this->db->bind('uniqid', $data['uniqid']);
$this->db->bind('urlid', $data['urlid']);
$this->db->bind('judul_content', $data['judul_content']);
$this->db->bind('visit_views', $data['visit_views']);
$this->db->bind('visitor_ip', $data['visitor_ip']);
$this->db->bind('waktu', $data['waktu']);

// execute perintahnya
$this->db->execute();
return $this->db->rowCount();  //return number
```

## Delete Data

```php
// lakukan query
$this->db->query('DELETE FROM ' . $this->table . ' WHERE id=:id');

// binding valuenya
$this->db->bind('id', $id);


// execute perintahnya
$this->db->execute();
return $this->db->rowCount();    //return number
```



{% hint style="info" %}
hati hati dalam penulisan query sering kali error saat beda white space atau spasi
{% endhint %}
