# architecture consept

## Introduction

by default Mini MVC PHP menggunakan pola atau presentation pattern MVC yaitu model view controller sebagai  structur base consepnya, dimana model akan merepresentasikan database , controler akan merepresentasikan bussiness model, dan view akan merepresentasikan tampilan. folder pada mini mvc php dipecah pecah berdasarkan fungsinya masing masing. penulisan mini mvc menggabungkan OOP dan Prosedural sebagai gaya programingnya.

## life circyle

### models

Models akan merepresetasikan database query. seperti framework lainnya. yang dibangun secara native code. semua core Pattern MVC diatur pada folder core

### controller

ontroller akan mereprentasikan bussiness model, seperti framework lainnya yang dibangun secara native code.semua core Pattern MVC diatur pada folder core

### view

view akan merepsentasikan view atau tampilan, by default saya tidak menggunakan template engine apapun untuk project ini namun saya coba implementasinya template engine Twig dari symfony.

### route

by default route pada mini mvc merepresentasikan _**domainname/controller/method/parameter**_  namun sudah saya tiadakan dan menggantinya dengan bramus router, jadi secara default untuk configurasi.

### command shell

nagara yeah that my last name, nagara adalah fiture command yang saya sediakan pada mini mvc php project, seperti membuat generate env, copy env, buat controller, model, view. untuk saat ini fitur ini terbatas.



## DIRECTORY

### storage

by default saya mengubah upload dir menjadi storage directory sebagai tempat menyimpan asset hasil upload, jadi asset static website di pisah dari public directory dan storage directory.

### public

by default saya membuat asset static itu berada pada folder public seperti css dan javascript.

### system

system directory atau folder system

### About

nothing saya belum kepikiran buat menuliskannya
