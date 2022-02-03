---
description: >-
  untuk frontend menggunakan fundamental dasar pengetahuan html css dan
  javascript saja, tidak menggunakan template engine
---

# basic html



### Introductions

secara default saya membuat structur saya sendiri atau gaya templating folder saya sendiri senyaman yang saya pakai, setelah lama berganti ganti style native front-end folder structure. akhirnya saya menemukannya dan menerapkannya pada project ini.

### writing structure view

contoh structur yang saya terapkan

* views
  * frontend
    * layout
      * header\_view.php
      * navbar\_view.php
      * footer\_view.php
    * pages
      * folderpage
        * FileView.php
  * auth
    * layout
      * header\_view.php
      * footer\_view.php
    * pages
      * signin\_view.php
      * signup\_view.php
  * backend
    * layout
    * pages

### Extending layout

view tetaplah view dan dibangun dengan format php, untuk melakukan extending layout bisa menggunakan build in function `view("namaview")` seperti contoh berikut ini .

example file _**home\_view.php**_

````php
<?= view('auth/layout/header_view') ?>
  <div id="app">
  
    ```
    
    content
    
    
    ```
  </div>
<?= view('auth/layout/footer_view') ?>
````

example _**header\_view.php**_

```markup
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta content="width=device-width, initial-scale=1, maximum-scale=1, shrink-to-fit=no" name="viewport">
  <title>Login &mdash; Stisla</title>

  <!-- General CSS Files -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css" integrity="sha384-fnmOCqbTlWIlj8LyTjo7mOUStjsKC4pOpQbqyi7RrhN7udi9RwhKkMHpvLbHG9Sr" crossorigin="anonymous">

</head>

<body>

```

example _**footer\_view.php**_

```markup
  <!-- General JS Scripts -->
  <script src="https://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery.nicescroll/3.7.6/jquery.nicescroll.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.24.0/moment.min.js"></script>

  <!-- JS Libraies -->

</body>
</html>

```

### passing data ke header or footer atau view lainnya ;

example berkas view nya **home.php**

````markup
<?= view('auth/layout/header_view',[
  "title" => $title,
  "meta" => $deskripsi,
]) ?>
  <div id="app">
  
    ```
    
    content
    
    
    ```
  </div>
<?= view('auth/layout/footer_view') ?>
````

example berkas headernya **header.php**

panggil data assoc dari keynya pada berkas

```markup
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta content="width=device-width, initial-scale=1, maximum-scale=1, shrink-to-fit=no" name="viewport">
  <meta name="description" content="<?= $deskripsi ?>">
  <title><?= $title ?></title>

  <!-- General CSS Files -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css" integrity="sha384-fnmOCqbTlWIlj8LyTjo7mOUStjsKC4pOpQbqyi7RrhN7udi9RwhKkMHpvLbHG9Sr" crossorigin="anonymous">

</head>

<body>

```
