# Modul step up Aerosemi MT36291 5V 1.5A

![[Step up Module 5V 1.5A MT36291 img1.png]]

| | |
|---|---|
| Jenis: | module power supply |
| Kegunaan: |  Step up power dari baterai |
| Output: | bisa diubah via jumper |
| Input: | 2.2V ~ 16V |
| Output: | up to 12V (datasheet IC up to 20V)|
| datasheet: | [pdf link luar](https://file.elecfans.com/web2/M00/43/3E/poYBAGJ864yAEltxAAuUiBhtEqk395.pdf "datasheet MT36291")
| marking : |  AL142 / FP6291 |

modul stepup berbasis chip MT36291. ada jumper untuk ubah output 5, 8, 9, 12V (default 12V)

note:
1. ubah tegangan dengan menyambung jumper A dan B (default tersambung dengan 0 ohm resistor) :

|Jumper A | Jumper B| V out|
|---|---|---|
|0|0|5V|
|0|1|8V|
|1|0|9V|
|1|1|12V|

2. Input harus **lebih kecil** dari output
3. Output enable ada di pin 4 IC tapi disambung langsung ke IN+ untuk auto start
4. Output enable LOW => Output == VIN
5. Output enable HIGH => Output == 5V

