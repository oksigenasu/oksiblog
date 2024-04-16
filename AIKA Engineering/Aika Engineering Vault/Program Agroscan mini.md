Lfitur dan komponen agroscan mini

#### Komponen
- [x] Sensor soil
- [x] GPS ublox neo 7
- [x] RS485 Transceiver
- [x] TTGO T display
- [x] tombol trigger ala2  # Stainless Steel Push Button Switch 22mm
- [x] Connector waterproof soil SD20 7Pin
- [x] wadah batre 18650
- [x] Stepup 5V
- [x] Casing tutup
- [ ] Silicon casing
- [x] pcb bolong
- [x] konektor JST SH 1mm 4P
- [x] konektor JST SH 1mm 3P
- [ ] Kabel awg 28

#### Fitur
- [x] Baca tegangan baterai
- [x] Baca Sensor Soil
- [x] Baca lokasi GPS
- [x] Konek ke WiFi
- [x] Konek ke server
- [x] Ambil settingan Alat dari server
- [x] Kirim data sensor ke server
- [x] simpan 100 data pengambilan terakhir
- [x] Akses point setting
- [x] halaman web setting
- [ ] halaman web download database
- [x] Display GUI nilai sensor
- [x] Display GUI setting alat 
- [ ] menu reconnect wifi
- [ ] menu pairing to server
- [ ] menu offline mode

fine tune:
- [x] kirim post code return diparsing jika error: 200 OK 300 Redirect 400 error 500 error
- [x] display smooth font
- [ ] 

##### format database
1. time_t dtm =0;
2. uint16_t probeCode =24177;
3. uint16_t landCode =0000;
4. uint16_t dataTake = 0;
5. uint16_t sampleCount = 0;
6. float lat= 112.345678f;
7. float lon= -7.89101f;
8. float temp = 99.9f;
9. float hum = 88.8f;
10. float ec = 0.555f;
11. float ph = 4.5f;
12. uint16_t nit = 111;
13. uint16_t pho = 222;
14. uint16_t kal = 333;
15. uint16_t dbNum = 0;