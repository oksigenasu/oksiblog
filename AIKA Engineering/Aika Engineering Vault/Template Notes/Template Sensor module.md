# Nama sensor {kegunaan}


Jenis: module sensor
Kegunaan:  sensor tegangan, arus, daya
Akses: I2C
Address: bisa diubah via jumper 
Logic level: 3v3 atau 5v

sensor tegangan dengan I2C. mudah dipakai tapi ukuran agak besar. 26V max input dengan resolusi 12bit.

note:
1. desain copy dari adafruit INA219
2. address I2C dapat diset menjadi :

|Jumper A0 | Jumper A1| address|
|---|---|---|
|0|0|0x40|
|1|0|0x41|
|0|1|0x44|
|1|1|0x45|

3. maksimal 4 sensor