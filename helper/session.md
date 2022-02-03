---
description: membuat helper untuk membuat session menggunakan build function
---

# session



## session start

session start() untuk mengaktifkan session

panggil session\_start() pada method contructor untuk mengaktifkan session pada setiap controllernya.

```php
public function __construct()
{
	// code here
	start_session();
}
```

## session destroy

session\_destroy() untuk mendestroy session atau menghapus session yang telah dibuat. atau bisa digunakan untuk method logout

```php
public function logout()
{
	// code here
	session_destroy();
	redirect("login");
}
```

## make session

make\_session() untuk membuat session.

```php
public function auth()
{
	// config session
	$session = [
		"username" => $_POST["username"],
		"login" => true,
	];
	
	// buat session
	make_session($session);
	
	// redirect session
	redirect("home");
}
```

## this session

this\_session() untuk melihat debug atau isi dari session

```php
public function home()
{
	// config session
	this_session(); // return debug session bentuk array
	
}
```

#### hasilnya akan seperti ini :

```php
"username" => "username",
"login" => true,
"_minimvc_session" => "ashdbjhbxzjgc1287gasda", // generate random
```
