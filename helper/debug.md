---
description: untuk debug
---

# debug



untuk debugging kamu bisa menggunakan 3 opsi

* **var\_dump(... some or variabel here);die;**
* **var\_dump(... some or variabel here);**
* **dump( ... some or variabel);**
* **dd( ... some or variabel here);**

contoh satu

```php
public function index()
{
	// echo "ini controller index";
	dd($_SERVER);
}
```

contoh dua

```php
public function index()
	{
		// echo "ini controller index";
		dump($_SERVER);
	}

```
