# BAHAN
1. Atmega 328P sebagai pengganti
2. wemos D1 Mini sebagai ESP8266 AVR ISP Programmer
3. Arduino IDE dengan Board Minicore
4. Kabel jumper
# SETTING Minicore 

  (install Arduino Minicore dulu)
  - Board: Minicore>Atmega328
  - Clock: External 11.0592Mhz
  - BOD: "BOD 1.8V" (karena pakai tegangan 3.3V)
  - EEPROM: EEPROM Retained
  - Compiler LTO: Disable
  - Variant: 328P/328PA
  - Bootloader: No (No Bootloader)
# CARA UPLOAD
 0. siapkan esp8266 AVR ISP Programmer dan tancapkan ke port ICSP Programmer
 1. nyalakan verbose output di arduino IDE
 ->File>preferences>show verbose output during [centang semua]
 3. upload bootloader dulu agar settingan atmega berjalan di 3.3V
 ->Tools>Burn Bootloader (cek di terminal command avrdude nya)
 ![[Upload ATMEGA WS Jeruk img1.png]]
 ```
 /home/oksigenasu/.arduino15/packages/MiniCore/tools/avrdude/7.1-arduino.1/bin/avrdude -C/home/oksigenasu/.arduino15/packages/MiniCore/hardware/avr/2.2.2/avrdude.conf -v -patmega328p -cstk500v1 -P/dev/ttyACM0 -b19200 -e -Ulock:w:0xff:m -Uefuse:w:0b11111110:m -Uhfuse:w:0b11010111:m -Ulfuse:w:0b11110111:m 
 ```
 ->ubah bagian -c(nama uploader) menjadi -c arduino
 ->ubah bagian -P(COM/Port) menjadi -Pnet:192.168.3.128:328 (atau alamat IP dari esp8266 AVR ISP)
 ```
/home/oksigenasu/.arduino15/packages/MiniCore/tools/avrdude/7.1-arduino.1/bin/avrdude -c arduino -C/home/oksigenasu/.arduino15/packages/MiniCore/hardware/avr/2.2.2/avrdude.conf -v -patmega328p -P net:192.168.3.128:328 -Uflash:w:/tmp/arduino_build_8880/WS_Jeruk_ATMEGA328.ino.with_bootloader.hex:i 
 ```
 ->jalankan command avrdude yg sudah diubah dari terminal
 ![[Upload ATMEGA WS Jeruk img7.png]]
 ![[Upload ATMEGA WS Jeruk img5.png]]
 4. upload program
 ->Sketch>Upload (cek lagi di terminal command avrdude nya)
 ![[Upload ATMEGA WS Jeruk img4.png]]
 `/home/oksigenasu/.arduino15/packages/MiniCore/tools/avrdude/7.1-arduino.1/bin/avrdude -C/home/oksigenasu/.arduino15/packages/MiniCore/hardware/avr/2.2.2/avrdude.conf -v -patmega328p -cstk500v1 -P/dev/ttyACM0 -b19200 -Uflash:w:/tmp/arduino_build_8880/WS_Jeruk_ATMEGA328.ino.with_bootloader.hex:i `
 ->ubah bagian -c(nama uploader) menjadi -c arduino
 ->ubah bagian -P(COM/Port) menjadi -Pnet:192.168.3.128:328 (atau alamat IP dari esp8266 AVR ISP)
 `/home/oksigenasu/.arduino15/packages/MiniCore/tools/avrdude/7.1-arduino.1/bin/avrdude -c arduino -C/home/oksigenasu/.arduino15/packages/MiniCore/hardware/avr/2.2.2/avrdude.conf -v -patmega328p -P net:192.168.3.128:328 -Uflash:w:/tmp/arduino_build_8880/WS_Jeruk_ATMEGA328.ino.with_bootloader.hex:i `
 ->jalankan command avrdude yg sudah diubah dari terminal
 ![[Upload ATMEGA WS Jeruk img6.png]]
  ![[Upload ATMEGA WS Jeruk img3.png]]
 5. test program dari linux nanopi dengan testcommand.py [WON/WOFF/READ]
![[Upload ATMEGA WS Jeruk img8.png]]

# PROGRAM
  ada 2 program
  1. program baca tegangan dari ADC 0
   ketika dapat perintah "READ/r" dari serial (format 12v = 1200.00)
  2. program trigger relay dan matikan relay
   ketika dapat perintah "WON/r" dan "WOFF/r" dari serial
  serial baudrate 115200

  pinout:
  - ADC0: baca tegangan dari resistor pembagi 12V ke 39K & 10K
  - GPIO8: Trigger Ampli (SSR1)
  - GPIO7: Trigger lamp (SSR2)
  - GPIO6: Trigger Camera (SSR3)
  - GPIO5: Trigger SSR4 (unused)
  - GPIO4: Trigger relay NC ground dari SSR1-SSR4 (SSR5)

```
#define AMP 8
#define LAMP 7
#define CAM 6
#define EMER 4

float multiplier = 4.9f; //(39K+10K)/10K

void setup() {
  Serial.begin(115200);
  pinMode(AMP, OUTPUT);
  pinMode(LAMP, OUTPUT);
  pinMode(CAM, OUTPUT);
  pinMode(EMER, OUTPUT);

}

void loop() {

  while (Serial.available() == 0) {} //kalo nggk ada serial, tunggu
  String teststr = Serial.readString(); //baca string
  teststr.trim(); //hilangkan spasi atau tab atau \r
  if (teststr == "WON") {
    digitalWrite(AMP, HIGH);
    Serial.print("ON");
  } else if (teststr == "WOFF") {
    digitalWrite(AMP, LOW);
    Serial.print("OFF");
  } else if (teststr == "READ") {
    int sensorValue = analogRead(A0);
    // Convert the analog reading (which goes from 0 - 1023) to a voltage (0 - 3.3V):
    float voltage = sensorValue * (3.3f / 1023.0f) * multiplier; // x multiplier biar jadi 12V langsung
    float sense = voltage * 100.0f;
    Serial.print(sense);
  }
}
```
