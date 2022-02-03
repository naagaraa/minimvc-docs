---
description: function result atau hasil query pada database
---

# result database

## Result Array

untuk result data dalam bentuk _array associative_ dibagi dua yaitu dalam bentuk _single_ data dan multiple data atau banyak data _row ._

### single

single menampilkan data secara single, biasanya digunakan untuk menampilkan data spesific

```php
public function getUserId($id)
{
	$this->db->query('SELECT * FROM ' . $this->table . ' WHERE id=:id');
	
	$this->db->bind('id', $id);
	return $this->db->singleArray();		// return Array Format
}
```

### row

row menampilkan data secara multiple atau banyak.

```php
public function getAllUser()
{

	$this->db->query('SELECT * FROM ' . $this->table);
	return $this->db->resultSetArray();    // return Array Format
}
```

## Result Object

untuk result data dalam bentuk obejct dibagi dua yaitu dalam bentuk _single_ data dan multiple data atau banyak data _row ._

### single

single menampilkan data secara single, biasanya digunakan untuk menampilkan data spesific

```php
public function getUserId($id)
{
	$this->db->query('SELECT * FROM ' . $this->table . ' WHERE id=:id');
	
	$this->db->bind('id', $id);
	return $this->db->singleObject();    // return Object Format
}
```

### row

row menampilkan data secara multiple atau banyak.

```php
public function getAllUser()
{
	$this->db->query('SELECT * FROM ' . $this->table);
	return $this->db->resultSetObject();  // return Object Format
}
```



## Result JSON

result dalam bentuk json yaitu menghasilkan data dari database dengan format json atau json encode

#### single

single menampilkan data secara single, biasanya digunakan untuk menampilkan data spesific

```php
public function getUserId($id)
{
	$this->db->query('SELECT * FROM ' . $this->table . ' WHERE id=:id');
	
	$this->db->bind('id', $id);
	return $this->db->singleJSON();   // return JSON FORMAT
}
```



#### row

row menampilkan data secara multiple atau banyak.

```php
public function getAllUser()
{
	$this->db->query('SELECT * FROM ' . $this->table);
	return $this->db->resultSetJSON();   // return JSON FORMAT
} 
```

