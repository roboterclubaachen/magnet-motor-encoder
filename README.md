# magnet-motor-encoder

## board-as5045b_rev10

### Motorencoder für axial befestigten diametralen Magneten

Motor-Encoder mit ams AS5045B.

Der AS5045B ist ein IC welcher die Ausrichtung eines über ihm befindlichen Magneten mit 12 Bit Auflösung erfasst.

An der Motorachse muss ein Ø 6 mm x 2.5 mm Magnet mit diametraler Orientierung befestigt werden, die zulässige Toleranz betrögt 0.1 mm.
Das Magnet ist exakt mittig über dem IC (welcher mittig auf der Platine platziert ist) ausgerichtet werden, der Toleranzbereich beträgt hier 0.25mm.

![AS5045B rev10 Bottom](img/board_as5045b_rev10_bottom.png)
![AS5045B rev10 Top](img/board_as5045b_rev10_top.png)

### Mechanische Dimensionen

![AS5045B rev10 Dimensionen](img/board_as5045b_rev10_dimensions.png)

Alle Angaben in Millimeter.

### Bauteile

Anzahl | Bauteil              | Bezeichnung / MPN
------ | -------------------- | -----------------------
1      | Magnetsensor IC      | AS5045B-ASSM
1      | Stecker Vorderseite  | [JST GH SM05B-GHS](https://www.digikey.de/product-detail/de/jst-sales-america-inc/SM05B-GHS-TB-LF-SN/455-1567-1-ND/807835) (1.25mm)
1      | Stecker Rückseite    | [JST GH BM05B-GHS](https://www.digikey.de/product-detail/de/jst-sales-america-inc/BM05B-GHS-TBT-LF-SN-N/455-1581-1-ND/807849) (1.25mm)
1      | LED Rot              | Bauform 0603
1      | LED Gelb             | Bauform 0603
2      | Vorwiderstand LED    | Bauform 0402
3 or 4 | Null-Ohm-Widerstand  | Bauform 0402
2      | Kondensator          | 2,2µF, >6,3V, X7R, Bauform 0603

### Stecker

Auf der Platine sind zwei 5-polige [JST GH](https://jst.de/product-family/show/89/gh) Stecker vorgesehen, welche Alternative bestückt werden können.
Der Stecker auf Vorderseite der Platine (wo auch der Sensor sitzt) bietet einen horizontalen Kabelausgang während auf der Rückseite ein vertikaler Kabelausgang vorgesehen ist.

Das Pinout beider Stecker ist identisch.

Pin | ABI-Interface | Serielles Interface
--- | ------------- | -------------------
 1  | A             | Data Out
 2  | +5V oder +3V3 | +5V oder +3V3
 3  | B             | Clock
 4  | I             | Chip Select (inverted)
 5  | GND           | GND

### Optionen / Konfiguration

#### Versorgungsspannung

Es sind sowohl 3,3V als auch 5V Versorgungsspannung möglich.
Die Versorgungsspannung muss mittels des einzigen Null-Ohm-Widerstands auf der Vorderseite (Beschriftung "3V") konfiguriert werden.

Spannung     | Null-Ohm-Widerstands (Beschriftung "3V")
------------ | ----------------------------------------
4,5V .. 5,5V | Nicht bestückt
3,0V .. 3,6V | Bestückt

#### Interface

Mittels Null-Ohm-Widerständen können wahlweise das ABI- oder das serielle Interface aktiviert werden.

![AS5045B rev10 Bottom Draufsicht](img/board-as5045b_rev10_bottom_vertical.png)

Zur Nutzung des ABI-Interfaces müssen die drei Null-Ohm-Widerstände innerhalb der blauen Markierung eingelötet werden.

Zur Aktivierung des seriellen Interfaces müssen die drei Null-Ohm-Widerstände innerhalb der roten Markierung eingelötet werden.

### Diagnose LEDs
* Rote und gelbe LEDs: Magnetfeldstärke
  * Aus: optimaler Betrieb
  * Gelb leuchtet: schwache Magnetfeldstärke, Magnet näher an IC platzieren.
  * Rot leuchtet: starke Magnetfeldstärke, Magnet weiter vom IC entfernt platzieren.
  * Rot und Gelb leuchten gleichzeitig: zu starkes oder zu schwaches Magnetfeld, keine zuverlässiger Betrieb möglich.

## board-as5045b

### Motorencoder für axial befestigten diametralen Magneten

Siehe [oben](#board-as5045b_rev10).

Die Platine ist hat exakt 22mm Durchmesser und sollte damit zu den *Namika* Motoren (ebenfalls 22mm Durchmesser) passen.
Das Magnet ist exakt mittig über dem IC, welcher mittig auf der Platine platziert ist, ausgerichtet werden.

### Diagnose LEDs
* Blaue LED: Power
* Rote und gelbe LEDs: Magnetfeldstärke
  * Aus: optimaler Betrieb
  * Gelb leuchtet: schwache Magnetfeldstärke, Magnet näher an IC platzieren.
  * Rot und Gelb leuchten: zu starkes oder zu schwaches Magnetfeld, keine zuverlässiger Betrieb möglich.

![AS5045B Board Bottom](img/board_as5045b_bottom.png)
![AS5045B Board Top](img/board_as5045b_top.png)

## board-as5304

### Motorencoder für axial befestigten mehrpoligen Ringmagneten

Motor-Encoder mit **ams** AS5304(A).

Der AS5304 ist ein IC welcher die Bewegung eines über ihm befindlichen mehrpoligen Magneten mit 160 Schritten pro Magnetpolpaar erfasst.
Die Platine ist hat etwa 12 mm Höhe und 39 mm Breite sowie ein 2mm Loch zu Ausrichtung über der Motorwelle.
Bei Bedarf kann dieses Loch aufgebohrt werden, in der Umgebung sind keine Leiterbahnen und kein Kupfer vorhanden.

An der Motorachse muss ein Ringmagnet mit 24 mm Innendurchmesser und 32 mm Außendurchmesser (-> MIttendurchmesser 28 mm) mittels eines nicht ferromagmetischen Werkstoffs befestigt werden.
Das Sensorarray im IC befindet sich exakt 28 mm vom Loch für die Motorachse entfernt, sodass die Platine bei Verwendung des oben genannten Magneten nur an der Motorachse und mit ca. 0.5 mm zum Ringmagnet ausgerichtet werden muss.

### Diagnose
* Blaue LED: Power
* Am Testpoint **AO** kann eine von der Magnetfeldstärke abhängige Spannung (gegen Testpoint **GND**) gemessen werden.

![AS5304 Board 3D Ansicht (mit KiCad gerendert)](img/board_as5304_3drender1.png)
![AS5304 Board Bottom](img/board_as5304_bottom.png)
![AS5304 Board Top](img/board_as5304_top.png)


## License

Copyright Raphael Lehmann 2016-2019

Licensed under CERN OHL v.1.2
