# Standarder for Centrabetjeningspanel tegning

## YouTube videoer til denne serie

* [OMJK](https://www.youtube.com/playlist?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [1. Betjeningspanel for OMJK's modelbane - Grundtavle med Sporplan](https://www.youtube.com/watch?v=dZjwpv8QaRw&list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1&index=1&pp=gAQBiAQBsAgC)
  * [2. Betjeningspanel for OMJK's modelbane - Huller for trykknapper 6x6 mm](https://youtu.be/PbYgpnhis6A?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [3. Betjeningspanel for OMJK's modelbane - Huller for trykknapper i sporplan](https://youtu.be/MnVt9wKIBpA?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [4. Betjeningspanel for OMJK's modelbane - Gruppering af huller for taster](https://youtu.be/W9_LvfxgKT4?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [5. Betjeningspanel for OMJK's modelbane - Fejlretning & tips](https://youtu.be/yiMUdccn0jY?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [6. Betjeningspanel for OMJK's modelbane - Sporskifte indikering](https://youtu.be/EQ77ScgAZLI?list=PLIsjLuvJr7uht_yYsS1T3RD3FGsFQwwR1)
  * [7. Betjeningspanel for OMJK's modelbane - Lidt oprydning i file structure]()
  * []()
  * []()
  * []()
  * []()

## Tavle

|Tavle|Sporplan|Sporplan Cut|Track Binder|Track Pad|Tavle med Track|
|:---:|:---:|:---:|:---:|:---:|:---:|
|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-10-54.png)|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-11-07.png)|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-11-48.png)|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-12-43.png)|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-13-20.png)|![](./Images/Tavle/Skærmbillede%20fra%202025-12-21%2019-13-58.png)|
|Z: 0,0mm|z: 0,0mm|Z: 6,0mm||||
|Pad: 6,0 mm||Pocket: 0,6mm||Pad: -0,6mm||
|||||||

* FreeCAD File:
  * [Tavle.FCStd](./Tavle.FCStd)

## Trykknapper

|6x6mm|12x12mm|
|:---:|:---:|
|![6x6mm](./Images/Trykknap/Skærmbillede%20fra%202025-12-21%2020-34-37.png)|![12x12mm](./Images/Trykknap/Skærmbillede%20fra%202025-12-21%2020-37-30.png)|

### Trykknap 6x6

|Knap|Octogon|Tryk|3D Layer|Total|
|:---:|:---:|:---:|:---:|:---:|
|![](./Images/Trykknap/Trykknap6x6_Knap.png)|![](./Images/Trykknap/Trykknap6x6_Octogon.png)|![](./Images/Trykknap/Trykknap6x6_Tryk.png)|![](./Images/Trykknap/Trykknap6x6_3D_Layer.png)|![](./Images/Trykknap/Trykknap6x6_3D_Model.png)|
||||||

* FreeCAD File:
  * [Trykknapper.FCStd](./Trykknapper.FCStd)
* Firkantet tact
  * 6x6mm
    * Trykknap
      * diameter: 6,5mm
      * Pad: 10mm
      * Z: -1,5mm
    * Octogon
      * diameter: 7,04mm
      * Pad: -3,0mm
      * Z: -3,0mm
    * Firkant
      * Bredde: 6,2mm
      * Pad: -2,0mm
      * Z: -4,0mm

## LED

* SK6812_5050
  * [DataSheet](https://cdn-shop.adafruit.com/product-files/2757/p2757_SK6812RGBW_REV01.pdf "Adafruit.com")

|Mechanical Dimensions|Pin Configuration|Typical Application Circuit|
|:---:|:---:|:---:|
|![SK6812_MechanicalDimensions](./Images/SK6812_MechanicalDimensions.png)|![SK6812_PinConfiguration](./Images/SK6812_PinConfiguration%20.png)|![SK6812_TypicalApplicationCircuit](./Images/SK6812_TypicalApplicationCircuit.png)
||||

### Sporskifte indikering

|PCB|SK6812 5050|Frirum|Glas|3D|
|:---:|:---:|:---:|:---:|:---:|
|![](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2011-41-23.png)|![](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2011-42-02.png)|![](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2013-39-30.png)|![Glas](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2011-42-19.png)|![3D](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2013-43-44.png)|
|Z: 0,0mm|Z: 1,5mm|z; 3,0mm|Z: 5,4mm|
|Pad: 1,5mm|Pad: -1,5mm||Pad: 0,6mm|
||||||

### Spor besat indikering

|PCB|SK6812 5050|Frirum|Glas|3D|
|:---:|:---:|:---:|:---:|:---:|
|![PCB](./Images/SporBesatIndikering/Skærmbillede%20fra%202025-12-22%2014-08-22.png)|![Led](./Images/SporBesatIndikering/Skærmbillede%20fra%202025-12-22%2014-09-00.png)|![Frirum](./Images/SporskifteLed/Skærmbillede%20fra%202025-12-22%2013-39-30.png)|![Glas](./Images/SporBesatIndikering/Skærmbillede%20fra%202025-12-22%2014-09-46.png)|![3D](./Images/SporBesatIndikering/Skærmbillede%20fra%202025-12-22%2014-18-34.png)|
|Z: 0,0mm|Z: 1,5mm|z; 3,0mm|Z: 5,4mm|
|Pad: 1,5mm|Pad: -1,5mm||Pad: 0,6mm|
||||||

### Blok indikering

|PCB Layer|Led Layer|Frirum|Glas Layer|Layer 3D|Total|
|:---:|:---:|:---:|:---:|:---:|:---:|
![PCB](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-17-17.png)|![SK6812](./Images/Block/Skærmbillede%20fra%202025-12-21%2011-34-02.png)|![Frirum](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-17-30.png)|![Glas](./Images/Block/Skærmbillede%20fra%202025-12-21%2017-04-43.png)|![3D](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-36-34.png)|![Total](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-38-03.png)|
|Z: 0,0mm|Z: 1,5mm|Z: 3,0mm|Z: 5,0mm|||
|Pad: 1,5mm|Pad: 1,5mm|AdditiveLoft|Pad: 1,0mm|||
|||Frirum/Glas||||
||||||

* FreeCAD File: 
  * [BlokIndikering_v1.FCStd](./BlokIndikering_v1.FCStd)

### PU-Signal

#### Symbol

|Sketch|Body|3D|
|:---:|:---:|:---:|
|![Sketch](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-05-36.png)|![Body](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-06-34.png)|![3D](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-06-46.png)|
||||

#### Led SK6812_5050 RGBWW

|PCB|Led 5050|Glas|3D|
|:---:|:---:|:---:|:---:|
|![PU_Led_PCB](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-28-14.png)|![PU_Led_Sketch001](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-28-46.png)|![PU_Led_Sketch002](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-29-07.png)|![PU_Led_3D](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-29-33.png)|
|||||

* FreeCAD File:
  * [Pu.FCStd](./Pu.FCStd)
