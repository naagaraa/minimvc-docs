---
description: >-
  by default pass update  fiture i'm add phinx migration agnostik libraries php
  for database migrations
---

# migrations



## Introduction

untuk menambah fiture agar lebih power full lagi MVC OOP PHP NATIVE nya saya menambahkan fiture migrations yang memungkinkan bisa membuat table schema pada code seperti orm milik laravel. by default migrations yang saya gunakanan adalah [phinx ](https://book.cakephp.org/phinx/0/en/index.html)

## Create migration

untuk membuat migration misa menggunakan commnad nagara, nama migration di tulis dengan PascalCase

{% hint style="danger" %}
untuk melakukan migration setting database pada berkas config.migrations.php
{% endhint %}

#### untuk [config migration database](broken-reference) lihat disini&#x20;

_**example :**_

```
php nagara buat:migration User
```

_**example :**_

```
php nagara buat:migration User_Logins
```

## Migrate&#x20;

untuk melakukan migrate data table

```
php nagara migrate
```

## Rollback&#x20;

untuk melakukan rollback

```
php nagara migrate:rollback
```

{% hint style="info" %}
migration not stabil . migration is new fiture
{% endhint %}
