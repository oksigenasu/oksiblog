# Ebyte E32 Lora Communication Module 433Mhz

![[Ebyte E32 Lora 433T20D img1.png]]
![[Ebyte E32 Lora 433T20D img2.png]]

| Jenis: |module komunikasi|
|---|---|
| Kegunaan: | komunikasi LoRa via serial|
| Akses: | Serial Rx Tx, Aux, Mode0 dan Mode1|
| Frekuensi: |400Mhz + 30 channel 1Mhz |
|Logic level: | 3v3|
|Library: | Ebyte Lora E32 Library |

Modul komunikasi Lora ke serial siap pakai. settingan tidak terlalu banyak tapi harus menggunakan module yang sama. ada 2 mode transmisi yaitu Transparent dan Fixed. untuk bisa saling komunikasi

### Mode Transmisi
![[Ebyte E32 Lora 433T20D img3.png]]

#### Transparent Transmission
- Kirim ke semua, terima dari semua asal masih dalam 1 Channel
- address tidak terpengaruh

#### Fixed Transmission
- Perlu address tujuan dan channel tujuan
- Hanya target pada channel tujuan yg menerima paket

#### Fixed Transmission: Broadcast
- Kirim ke semua address dalam sebuah channel
- kirim ke broadcast address FFFF (255)
- dapat menggunakan fungsi library E32  <``sendBroadcastFixedMessage(0x04,"Broadcast message to channel 04")``>
#### Fixed Transmission: Broadcast
- terima dari semua address dalam 1 channel
- set address device menjadi broadcast address FFFF

### Note:
1. gunakan fixed transmission jika perlu pindah2 channel
2. selalu samakan FEC atau **Forward Error Correction Switch**
3. selalu simpan / tampilkan address device dan tujuan address
4. SELALU SAMAKAN TIPE MODULE
