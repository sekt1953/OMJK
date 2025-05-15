# Hjulby Pult Led

## Kilde

* Hjulby_Klemrække Led:
  * [Hjulby_Pult_Klemrække_B.pdf](./Kilde/Hjulby_Pult_Klemrække_B.pdf)
  * [Hjulby_Pult_Klemrække_C.pdf](./Kilde/Hjulby_Pult_Klemrække_C.pdf)
  * [Hjulby_Pult_Klemrække_D.pdf](./Kilde/Hjulby_Pult_Klemrække_D.pdf)
  * [Hjulby_Pult_Klemrække_E.pdf](./Kilde/Hjulby_Pult_Klemrække_E.pdf)
* Hjulby_Klemrække Led antal total: 96
  * Hjulby_Klemrække_B:
    * [Signal Led: 20](./Hjulby_Pult_Led.md#signalled)
  * Hjulby_Klemrække_C:
    * [Signal Led: 25](./Hjulby_Pult_Led.md#signalled)
  * Hjulby_Klemrække_D:
    * Lampe: 1
    * [Sporbesættelse: 25+10](Hjulby_Pult_Led.md#sporbesættelseled/)
    * [Sporskifter: 18](./Hjulby_Pult_Led.md#sporskifteled)
  * Hjulby_Klemrække_E:
    * [Togvejslamper: 32+10](./Hjulby_Pult_Led.md#togvejsled)

## SignalLed

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
|D|1|Lampe ved Grøn knap R|/||ju-sl-_x0_15|
|D|2|Lampe ved Grøn knap R|/|GND||
|D|3||/|||
|D|4||/|||
|D|5||/|||
|D|6||/|||
|D|7||/|||
|D|8||/|||
|D|9||/|||

## SporbesættelseLed

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---|:---|:---:|:---:|:---|
|D|10|Sporbesættelse fældes +5V|/|Sporbesættelse fældes +5V||
|D|11|B61-Rød|/|_x0_14||
|D|12|A61-Rød|/|_x0_13||
|D|13|K12-Rød|/|_x0_12||
|D|14|M12-Rød|/|_x0_11||
|D|15|01-Rød|/|_x0_10||
|D|16|02-Rød|/|_x0_09||
|D|17|03-Rød|/|NB! 5 led||
|D|18|04-Rød|/|NB! 2 Led||
|D|19|05-Rød|/|_x0_06||
|D|20|06-Rød|/|_x0_05||
|D|21|08-Rød|/|_x0_04||
|D|22|09-Rød|/|_x0_03||
|D|23|10-Rød|/|_x0_02||
|D|24|11-Rød|/|NB! 5 led||
|D|25|12-Rød|/|_x0_00||
|D|26|13-Rød|/|_x1_15||
|D|27|14-Rød|/|_x1_14||
|D|28|15-Rød|/|_x1_13||
|D|29|16-Rød|/|NB! 2 led||
|D|30|17-Rød|/|_x1_11||
|D|31|19-Rød|/|_x1_10||
|D|32|A12-Rød|/|_x1_09||
|D|33|D61-Rød|/|_x1_08||
|D|34|C12-Rød|/|_x1_07||
|D|35|C61-Rød|/|_x1_06||
|D|36||/|||
|D|37||/|||

## SporskifteLed

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---|:---|:---:|:---:|:---|
|D|38|101a|/|_x1_05|_45|
|D|39|101a|/|_x1_04|_44|
|D|40|101b|/|_x1_03|_43|
|D|41|101b|/|_x1_02|_42|
|D|42|102a|/|_x1_01|_41|
|D|43|102a|/|_x1_00|_40|
|D|44|102b|/|_x2_15|_3F|
|D|45|102b|/|_x2_14|_3E|
|D|46|S3|/|_x2_13|_3D|
|D|47|S3|/|_x2_12|_3C|
|D|48|104a|/|_x2_11|_3B|
|D|49|104a|/|_x2_10|_3A|
|D|50|104b|/|_x2_09|_39|
|D|51|104b|/|_x2_08|_38|
|D|52|105a|/|_x2_07|_37|
|D|53|105a|/|_x2_06|_36|
|D|54|105b|/|_x2_05|_35|
|D|55|105b|/|_x2_04|_34|
|D|56||/|||

## TogvejsLed

|Klemrække|Pin|Signal Led|/|MCU Terminal Addr.|Entites Name|
|:---:|:---|:---|:---:|:---:|:---|
|E|1|Togvejsfældes +5V|/|+5V||
|E|2|B61-Grøn|/|_y0_15||
|E|3|K12-Grøn|/|_y0_14||
|E|4|01-Grøn|/|_y0_13||
|E|5|02-Grøn|/|_y0_12||
|E|6|03-Grøn|/|NB! 5 led||
|E|7|04-Grøn|/|NB! 2 Led||
|E|8|05-Grøn|/|_y0_09||
|E|9|06-Grøn|/|_y0_08||
|E|10|07-Grøn|/|_y0_07||
|E|11|08-Grøn|/|_y0_06||
|E|12|09-Grøn|/|_y0_05||
|E|13|10-Grøn|/|_y0_04||
|E|14|11-Grøn|/|NB! 5 led||
|E|15|12-Grøn|/|_y0_02||
|E|16|13-Grøn|/|_y0_01||
|E|17|14-Grøn|/|_y0_00||
|E|18|Togvejsfældes +5V|/|+5V||
|E|19|15-Grøn|/|_y1_15||
|E|20|16-Grøn|/|_y1_14||
|E|21|17-Grøn|/|_y1_13||
|E|22|19-Grøn|/|_y1_12||
|E|23|A12-Grøn|/|_y1_11||
|E|24|C12-Grøn|/|_y1_10||
|E|25|C61-Grøn|/|_y1_09||
|E|26|C61|/|_y1_08||
|E|27|C61|/|_y1_07||
|E|28|S3|/|_y1_06||
|E|29|S3|/|_y1_05||
|E|30|S3|/|_y1_04||
|E|31|Hvid-Spsk omst|/|_y1_03||
|E|32|Hvid-Blinkkontrol|/|_y1_02||
|E|33|Hvid-Understatiom drift|/|_y1_01||
|E|34|Rød-OVK10|/|_y1_00||
|E|35||/|||
|E|36||/|||
|E|37||/|||
|E|38||/|||
|E|39||/|||
|E|40||/|||
|E|41||/|||
|E|42||/|||
|E|43||/|||
|E|44||/|||
|E|45||/|||
|E|46||/|||
|E|47||/|||
|E|48||/|||
|E|49||/|||
|E|50||/|||
|E|51||/|||
|E|52||/|||
|E|53||/|||
|E|54||/|||
|E|55||/|||
|E|56||/|||
