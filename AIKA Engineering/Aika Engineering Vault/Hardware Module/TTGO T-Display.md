# Modul TTGO T-Display IPS ESP32

Foto board /bentuk module
![[TTGO T-Display img1.png]]
Foto keterangan pinout
![[TTGO T-Display img2.png]]

|Jenis: |Module / Microcontroller / Display|
|---|---|
|Kegunaan: |Wifi, Bluetooth, Display, IoT, low power, Arduino|
|Koneksi fisik:| pinheader, usb C, jst battery|
|Fitur: |Wifi, BT, Display, button x2, voltage detection|

Keterangan:
modul sismin [[esp32]] dengan display usb micro C dan pinout breakout. layar IPS ukuran 1.14" dengan onboard tombol dan voltage detection . tersedia variasi PSRAM 4Mb/16Mb. ukuran kecil dan warna terang

Project:
1. [[Agrobot Agroscan Mini]]
2. link project 2
3. link projet3

Note:
1. sama dengan [[esp32]]
2. usb menggunakan ch9102 (compatible dgn CP2104)
3. Tombol: l006+I007 (perlu dicek), battery power detection
4. pin 5V terhubung dgn Vusb dan Vbat (jadi perlu step up utk bisa 5V)
5. library TFT eSPI tersedia di github
6. beberapa GPIO adalah input only