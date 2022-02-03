# upload directory



### upload\_dir()

upload dir adalah function yang dibuat untuk mengarahkan ke root foldernya yaitu storage&#x20;

```php
<?php
$filename = $data["image"]["name"];
$pathfile = upload_dir("image") . $filename . png; 

// return path file
// document root/storage/image/gambar.png
```
