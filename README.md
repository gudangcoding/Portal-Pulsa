Cara Penggunaan API portal Pulsa Menggunakan LARAVEL VERSI 5


----------


Package for Laravel 5
untuk petunjuk api bisa dikunjungi website dari portal pulsa di bawah ini
[Official Documentation](http://portalpulsa.com/api-transaksi-pulsa-murah/)
Installation

# pada folder project anda, download libray ini memnggunakan cmd dengan mengetikkan perinah berikut :
```
    composer require azioarv/portalpulsa
```
#setelah berhasil terdownload mengunakan composer maka setting lagi penggunaannya pada folder config
Tambahkan KOde berikut pada file config/app.php

Pada Provider tambahkan kode berikut di baris akhir
```php
AzioArv\PortalPulsa\PortalPulsaServiceProvider::class
```
//untuk Aliases tambahkan kode berikut

```php
'Pulsa' => AzioArv\PortalPulsa\PortalPulsaFacade::class
```
Jalankan perintah dibawah ini untuk menyelesaikan konfigurasi

    php artisan vendor publish
    
setting id key dan secret yang anda dapat dari member anda di portal pulsa
.env

    PULSA_ID=id kamu
    PULSA_KEY=keykamu
    PULSA_SECRET=secretkamu

untuk  Check Saldo
```php
Pulsa::saldo();
```
Check harga Produk
```php
Pulsa::cekHarga($productCode);
```
Check Status transaksi
```php
Pulsa::status($transcationID);
```
Proses pembelian pulsa
```php
Pulsa::prosesPulsa($productCode,$phoneNumber,$transactionID);
```
Proses pembelian PLN
```php
Pulsa::prosesPLN($productCode,$phoneNumber,$plnNumber,$transactionID);
```
