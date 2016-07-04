# magnet-motor-encoder

### Motorencoder für axial befestigten diametralen Magneten

Motor-Encoder mit **ams** AS5045B.

Der AS5045B ist ein IC welcher die Ausrichtung eines über ihm befindlichen Magneten mit 12 Bit Auflösung erfasst.
Die Platine ist hat exakt 22mm Durchmesser und sollte damit zu den *Namika* Motoren (ebenfalls 22mm Durchmesser) passen.

An der Motorachse muss ein Ø 6 mm x 2.5 mm Magnet mit diametraler Orientierung befestigt werden, die zulässige Toleranz betrögt 0.1 mm.
Das Magnet ist exakt mittig über dem IC (welcher mittig auf der Platine platziert ist) ausgerichtet werden, der Toleranzbereich beträgt hier 0.25mm.

### Diagnose LEDs
* Blaue LED: Power
* Rote und gelbe LEDs: Magnetfeldstärke
  * Aus: optimaler Betrieb
  * Gelb leuchtet: schwache Magnetfeldstärke, Magnet näher an IC platzieren.
  * Rot und Gelb leuchten: zu starkes oder zu schwaches Magnetfeld, keine zuverlässiger Betrieb möglich.

