keluhan:
1. matot (tidak bisa nyala)
2. baterai tidak terdeteksi
3. (dulu) mau nyala hanya pake charger
4. terakhir dicoba pake charger temen bisa nyala charging lamp nya, tapi tetep nggk nyala

diagnosa awal:
1. check 19V dari charger = tidak ada
2. check 19V dengan PSU = 19V masuk, tegangan VIN cuma +-1V

hipotesa:
1. ~~IC charger rusak?~~ 
2. IC stepdown rusak?
3. IC IO rusak?

checked:
1. ganti IC charger, tegangan VIN masih sekitar 1V naik turun
2. sinyal ACOK dari charger masih LOW (harusnya kalau pakai adaptor jadi HIGH)
3. kemungkinan ada proteksi (short circuit) dari IC charger.

to check:
1. Isolasi VIN dari stepdown
- copot PL8012 & PL8013 (3VPCU & 5VPCU) lalu cek mosfet
  ![[repair-acer-aspire-v5-591-series_img1.png]]
 ![[repair-acer-aspire-v5-591-series_img2.png]]

tools:
- schematic: Quanta ZRY r1A
- boardview: acer-v15-t500-da0zrymb8g0-zry-board-view-pdf
- datasheet BQ24780S (ic charger)

#repair #laptop