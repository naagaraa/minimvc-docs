---
description: input file menggunakan metod POST dan GET
---

# input

## Introduction

untuk melakukan sanitaze yang tidak berulang ditulis secara native , saya menambahkan sanitasize untuk decode script html tag untuk menghandle xss atau membuat prevent xss dari payload. menginputkan script payload html tidak akan dieksekusi, melaikan akan dirubah ke dalam bentuk string.

### Basic usage

```
# call class
use MiniMvc\Apps\Core\Bootstraping\Request;

# used method | example post()
$data = Request::post("name");
```

### post()

untuk metode $\_POST

```
$data = Request::post("name");
```



### get()

untuk metode $\_GET

```
$data = Request::get("name");
```

### html()

untuk metode $\_POST untuk character html code, dan biasanya digunakan dengan text-editor atau wysg.

```
$data = Request::html("name");
```

