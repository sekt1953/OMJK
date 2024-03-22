# Hjulby_Signal_led

## Kilde

* Hjulby_Klemrække Signal
  * [Hjulby_Klemrække_B.pdf](./Kilde/Hjulby_Klemrække_B.pdf)
  * [Hjulby_Klemrække_C.pdf](./Kilde/Hjulby_Klemrække_C.pdf)
  * [Hjulby_Klemrække_D.pdf](./Kilde/Hjulby_Klemrække_D.pdf)

## Signal Led -> PCA9685 (46 signal led)

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---:|:---|:---:|:---:|:---|
||1|A-Øverste-Gul+|/||ju-sl-00_A-Øverste-Gul|
||2|A-Øverste-Gul-|/|GND||
||3|A-Øverste-Grøn+|/||ju-sl-00_A-Øverste-Grøn|
||4|A-Øverste-Grøn-|/|GND||
||5|A-Rød+|/||ju-sl-00_A-Rød|
||6|A-Rød-|/|GND||
||7|A-Nederste-Grøn+|/||ju-sl-00_A-Nederste-Grøn|
||8|A-Nederste-Grøn-|/|GND||
||9|A-˅+|/||ju-sl-00_A-˅|
||10|A-˅-|/|GND||
||11|A-˄+|/||ju-sl-00_A-˄|
||12|A-˄-|/|GND||
||13|A-І+|/||ju-sl-00_A-І|
||14|A-І-|/|GND||
||15||/|||
||16|B-Rød+|/||ju-sl-00_B-Rød|
||17|B-Rød-|/|GND||
||18|B-Grøn-+|/||ju-sl-00_B-Grøn|
||19|B-Grøn--|/|GND||
||20|B-Hvid-+|/||ju-sl-00_B-Hvid|
||21|B-Hvid-|/|GND||
||22||/|||
||23|C-Øverste-Grøn|/||ju-sl-00_C-Øverste-Grøn|
||24|C-Øverste-Grøn|/|GND||
||25|C-Rød|/||ju-sl-00_C-Rød|
||26|C-Rød|/|GND||
||27|C-Nederste-Grøn|/||ju-sl-00_C-Nederste-Grøn|
||28|C-Nederste-Grøn|/|GND||
||29||/|||
||30|Lampe ved Grøn knap R|/||ju-sl-00_Lampe ved Grøn knap R|
||31|Lampe ved Grøn knap R|/|GND||
||32||/|||
||33|D-Rød|/||ju-sl-00_D-Rød|
||34|D-Rød|/|GND||
||35|D-Grøn|/||ju-sl-00_D-Grøn|
||36|D-Grøn|/|GND||
||37|D-Hvid|/||ju-sl-00_D-Hvid|
||38|D-Hvid|/|GND||
||39||/|||
||40|E1-Rød|/||ju-sl-00_E1-Rød|
||41|E1-Rød|/|GND||
||42|E1-Grøn|/||ju-sl-00_E1-Grøn|
||43|E1-Grøn|/|GND||
||44|E1-Hvid|/||ju-sl-00_E1-Hvid|
||45|E1-Hvid|/|GND||
||46||/|||
||47|E3-Rød|/||ju-sl-00_E3-Rød|
||48|E3-Rød|/|GND||
||49|E3-Grøn|/||ju-sl-00_E3-Grøn|
||50|E3-Grøn|/|GND||
||51|E3-Hvid|/||ju-sl-00_E3-Hvid|
||52|E3-Hvid|/|GND||
||53||/|||
||54|F2-Rød|/||ju-sl-00_F2-Rød|
||56|F2-Rød|/|GND||
||57|F2-Grøn|/||ju-sl-00_F2-Grøn|
||58|F2-Grøn|/|GND||
||59|F2-Hvid|/||ju-sl-00_F2-Hvid|
||60|F2-Hvid|/|GND||
||61||/|||
||62|F3-Rød|/||ju-sl-00_F3-Rød|
||63|F3-Rød|/|GND||
||64|F3-Grøn|/||ju-sl-00_F3-Grøn|
||65|F3-Grøn|/|GND||
||66|F3-Hvid|/||ju-sl-00_F3-Hvid|
||67|F3-Hvid|/|GND||
||68||/|||
||69|G-Øverste-Grøn|/||ju-sl-00_G-Øverste-Grøn|
||70|G-Øverste-Grøn|/|GND||
||71|G-Rød|/||ju-sl-00_G-Rød|
||72|G-Rød|/|GND||
||73|G-Nederste-Grøn|/||ju-sl-00_G-Nederste-Grøn|
||74|G-Nederste-Grøn|/|GND||
||75||/|||
||76|H-Rød|/||ju-sl-00_H-Rød|
||77|H-Rød|/|GND||
||78|H-Grøn|/||ju-sl-00_H-Grøn|
||79|H-Grøn|/|GND||
||80|H-Hvid|/||ju-sl-00_H-Hvid|
||81|H-Hvid|/|GND||
||82||/|||
||83|J-Øverste-Gul|/||ju-sl-00_J-Øverste-Gul|
||84|J-Øverste-Gul|/|GND||
||85|J-Øverste-Grøn|/||ju-sl-00_J-Øverste-Grøn|
||86|J-Øverste-Grøn|/|GND||
||87|J-Rød|/||ju-sl-00_J-Rød|
||88|J-Rød|/|GND||
||89|J-Nederste-Grøn|/||ju-sl-00_J-Nederste-Grøn|
||90|J-Nederste-Grøn|/|GND||
||91|J-˅|/||ju-sl-00_J-˅|
||92|J-˅|/|GND||
||93|J-˄|/||ju-sl-00_J-˄|
||94|J-˄|/|GND||
||95|J-І|/||ju-sl-00_J-І|
||96|J-І|/|GND||
||97||/|||
||98|K-Rød|/||ju-sl-00_K-Rød|
||99|K-Rød|/|GND||
||100|K-Grøn|/||ju-sl-00_K-Grøn|
||101|K-Grøn|/|GND||
||102|K-Hvid|/||ju-sl-00_K-Hvid|
||103|K-Hvid|/|GND||
