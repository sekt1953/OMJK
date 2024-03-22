# Hjulby Pult Led

## Kilde:

* Hjulby_Klemrække Signal
  * [Hjulby_Klemrække_B.pdf](./Kilde/Hjulby_Klemrække_B.pdf)
  * [Hjulby_Klemrække_C.pdf](./Kilde/Hjulby_Klemrække_C.pdf)
  * [Hjulby_Klemrække_D.pdf](./Kilde/Hjulby_Klemrække_D.pdf)

## Pult Signal Led -> PCA9685 (46 signal led)

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---:|:---|:---:|:---:|:---|
|B|11|A-Øverste-Gul+|/||ju-sl-00_A-Øverste-Gul|
|B|12|A-Øverste-Gul-|/|GND||
|B|13|A-Øverste-Grøn+|/||ju-sl-00_A-Øverste-Grøn|
|B|14|A-Øverste-Grøn-|/|GND||
|B|15|A-Rød+|/||ju-sl-00_A-Rød|
|B|16|A-Rød-|/|GND||
|B|17|A-Nederste-Grøn+|/||ju-sl-00_A-Nederste-Grøn|
|B|18|A-Nederste-Grøn-|/|GND||
|B|19|A-˅+|/||ju-sl-00_A-˅|
|B|20|A-˅-|/|GND||
|B|21|A-˄+|/||ju-sl-00_A-˄|
|B|22|A-˄-|/|GND||
|B|23|A-І+|/||ju-sl-00_A-І|
|B|24|A-І-|/|GND||
|B|25||/|||
|B|26|B-Rød+|/||ju-sl-00_B-Rød|
|B|27|B-Rød-|/|GND||
|B|28|B-Grøn-+|/||ju-sl-00_B-Grøn|
|B|29|B-Grøn--|/|GND||
|B|30|B-Hvid-+|/||ju-sl-00_B-Hvid|
|B|31|B-Hvid-|/|GND||
|B|32||/|||
|B|33|C-Øverste-Grøn|/||ju-sl-00_C-Øverste-Grøn|
|B|34|C-Øverste-Grøn|/|GND||
|B|35|C-Rød|/||ju-sl-00_C-Rød|
|B|36|C-Rød|/|GND||
|B|37|C-Nederste-Grøn|/||ju-sl-00_C-Nederste-Grøn|
|B|38|C-Nederste-Grøn|/|GND||
|B|39||/|||
|B|40|Lampe ved Grøn knap R|/||ju-sl-00_Lampe ved Grøn knap R|
|B|41|Lampe ved Grøn knap R|/|GND||
|B|42||/|||
|B|43|D-Rød|/||ju-sl-00_D-Rød|
|B|44|D-Rød|/|GND||
|B|45|D-Grøn|/||ju-sl-00_D-Grøn|
|B|46|D-Grøn|/|GND||
|B|47|D-Hvid|/||ju-sl-00_D-Hvid|
|B|48|D-Hvid|/|GND||
|B|49||/|||
|B|50|E1-Rød|/||ju-sl-00_E1-Rød|
|B|51|E1-Rød|/|GND||
|B|52|E1-Grøn|/||ju-sl-00_E1-Grøn|
|B|53|E1-Grøn|/|GND||
|B|54|E1-Hvid|/||ju-sl-00_E1-Hvid|
|B|55|E1-Hvid|/|GND||
|B|56||/|||
|/|/|/|/|/|/|
|C|1|E3-Rød|/||ju-sl-00_E3-Rød|
|C|2|E3-Rød|/|GND||
|C|3|E3-Grøn|/||ju-sl-00_E3-Grøn|
|C|4|E3-Grøn|/|GND||
|C|5|E3-Hvid|/||ju-sl-00_E3-Hvid|
|C|6|E3-Hvid|/|GND||
|C|7||/|||
|C|8|F2-Rød|/||ju-sl-00_F2-Rød|
|C|9|F2-Rød|/|GND||
|C|10|F2-Grøn|/||ju-sl-00_F2-Grøn|
|C|11|F2-Grøn|/|GND||
|C|12|F2-Hvid|/||ju-sl-00_F2-Hvid|
|C|13|F2-Hvid|/|GND||
|C|14||/|||
|C|15|F3-Rød|/||ju-sl-00_F3-Rød|
|C|16|F3-Rød|/|GND||
|C|17|F3-Grøn|/||ju-sl-00_F3-Grøn|
|C|18|F3-Grøn|/|GND||
|C|19|F3-Hvid|/||ju-sl-00_F3-Hvid|
|C|20|F3-Hvid|/|GND||
|C|21||/|||
|C|22|G-Øverste-Grøn|/||ju-sl-00_G-Øverste-Grøn|
|C|23|G-Øverste-Grøn|/|GND||
|C|24|G-Rød|/||ju-sl-00_G-Rød|
|C|25|G-Rød|/|GND||
|C|26|G-Nederste-Grøn|/||ju-sl-00_|G-Nederste-Grøn
|C|27|G-Nederste-Grøn|/|GND||
|C|28||/|||
|C|29|H-Rød|/||ju-sl-00_H-Rød|
|C|30|H-Rød|/|GND||
|C|31|H-Grøn|/||ju-sl-00_H-Grøn|
|C|32|H-Grøn|/|GND||
|C|33|H-Hvid|/||ju-sl-00_H-Hvid|
|C|34|H-Hvid|/|GND||
|C|35||/|||
|C|36|J-Øverste-Gul|/||ju-sl-00_J-Øverste-Gul|
|C|37|J-Øverste-Gul|/|GND||
|C|38|J-Øverste-Grøn|/||ju-sl-00_J-Øverste-Grøn|
|C|39|J-Øverste-Grøn|/|GND||
|C|40|J-Rød|/||ju-sl-00_J-Rød|
|C|41|J-Rød|/|GND||
|C|42|J-Nederste-Grøn|/||ju-sl-00_J-Nederste-Grøn|
|C|43|J-Nederste-Grøn|/|GND||
|C|44|J-˅|/||ju-sl-00_J-˅|
|C|45|J-˅|/|GND||
|C|46|J-˄|/||ju-sl-00_J-˄|
|C|47|J-˄|/|GND||
|C|48|J-І|/||ju-sl-00_J-І|
|C|49|J-І|/|GND||
|C|50||/|||
|C|51|K-Rød|/||ju-sl-00_K-Rød|
|C|52|K-Rød|/|GND||
|C|53|K-Grøn|/||ju-sl-00_K-Grøn|
|C|54|K-Grøn|/|GND||
|C|55|K-Hvid|/||ju-sl-00_K-Hvid|
|C|56|K-Hvid|/|GND||
|/|/|/|/|/|/|
|D|1|Lampe ved Grøn knap R|/||ju-sl-00_|
|D|2|Lampe ved Grøn knap R|/|GND||
|D|3||/|||
|D|4||/|||
|D|5||/|||
|D|6||/|||
|D|7||/|||
|D|8||/|||
|D|9||/|||

## Sporbesættelse- & Sporskifte-Led -> PCA9685 (25 + 18 led)

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---|:---|:---:|:---:|:---|
|D|10|Sporbesættelse fældes +5V|/|Sporbesættelse fældes +5V||
|D|11||/|||
|D|12||/|||
|D|13||/|||
|D|14||/|||
|D|15||/|||
|D|16||/|||
|D|17||/|||
|D|18||/|||
|D|19||/|||
|D|20||/|||
|D|21||/|||
|D|22||/|||
|D|23||/|||
|D|24||/|||
|D|25||/|||
|D|26||/|||
|D|27||/|||
|D|28||/|||
|D|29||/|||
|D|30||/|||
|D|31||/|||
|D|32||/|||
|D|33||/|||
|D|34||/|||
|D|35||/|||
|D|36||/|||
|D|37||/|||
|D|38||/|||
|D|39||/|||
|D|40||/|||
|D|41||/|||
|D|42||/|||
|D|43||/|||
|D|44||/|||
|D|45||/|||
|D|46||/|||
|D|47||/|||
|D|48||/|||
|D|49||/|||
|D|50||/|||
|D|51||/|||
|D|52||/|||
|D|53||/|||
|D|54||/|||
|D|55||/|||
|D|56||/|||
