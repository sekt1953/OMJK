# Standarder for Centrabetjeningspanel tegning

## Trykknapper

### Trykknap 6x6

|Knap|Octogon|Tryk|3D Layer|Total|
|:---:|:---:|:---:|:---:|:---:|
|![](./Images/Trykknap/Trykknap6x6_Knap.png)|![](./Images/Trykknap/Trykknap6x6_Octogon.png)|![](./Images/Trykknap/Trykknap6x6_Tryk.png)|![](./Images/Trykknap/Trykknap6x6_3D_Layer.png)|![](./Images/Trykknap/Trykknap6x6_3D_Model.png)|

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



### Blok indikering

Denne model bruges til at lave hul i frontpladen for blok indikering.  
Den Klones i **FreCAD Part Design** med **Clone** funktionen  
Anbringes det rigtige sted på sporplanen,  
i **FreeCAD Part** kan bruges sammen med **Union** & **Cut** funktionen.

#### Blok indikering v1

|PCB Layer|Led Layer|Frirum|Glas Layer|Layer 3D|Total|
|:---:|:---:|:---:|:---:|:---:|:---:|
![PCB](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-17-17.png)|![SK6812](./Images/Block/Skærmbillede%20fra%202025-12-21%2011-34-02.png)|![Frirum](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-17-30.png)|![Glas](./Images/Block/Skærmbillede%20fra%202025-12-21%2017-01-15.png)|![3D](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-36-34.png)|![Total](./Images/Block/Skærmbillede%20fra%202025-12-21%2016-38-03.png)|
|Z: 0,0mm|Z: 1,5mm|Z: 3,0mm|Z: 5,0mm|||
|Pad: 1,5mm|Pad: 1,5mm|AdditiveLoft|Pad: 1,0mm|||
|||Frirum/Glas||||

* FreeCAD File: 
  * [BlokIndikering_v1.FCStd](./BlokIndikering_v1.FCStd)

#### Blok indikering v2

|PCB|Led Layer|Led Layer2|Glas Layer|Layer 3D|Total|
|:---:|:---:|:---:|:---:|:---:|:---:|
|![BlockSignal_Pcb](./Images/Block/BlockSignal_PCB_v2.png)|![BlockSignal_Led](./Images/Block/BlockSignal_Led_v2.png)|![BlockSignal_Led](./Images/Block/BlockSignal_Led2_v2.png)|![BlockSignal_Glas](./Images/Block/BlockSignal_Glas_v2.png)|![BlockSignal_Layer3D](./Images/Block/BlockSignal_Layer3D_v2.png)|![BlockSignal_3D_Model](./Images/Block/BlockSignal_3D_Model2.png)|

* FreeCAD File: 
  * [BlockSignal.FCStd](./BlockSignal.FCStd) 
* How to
  * Belysning:
    * LED: SK6812_5050_RGBWW
    * Montage: hjemmelavet print
  * Layer
    * Position Z:  
      * Base: 0,00mm
      * PCB: 0,00mm
      * Led: 3,00mm
      * Led2: 3,00mm
      * Glas: 5,00mm
    * Pad
      * Base:
        * Length: 6,00mm
        * Reversed: No
      * PCB:
        * Length: 1,50mm
        * Reversed: No
      * Led:
        * Length: 1,50mm
        * Reversed: Yes
      * Led:
        * Length: 1,50mm
        * Reversed: Yes
      * Glas:
        * Length: 0,00mm
        * Reversed: No
    * AdditiveLoft:
      * Layer:
        * Led2
        * Glas

### PU-Signal

#### Symbol

|Sketch|Body|3D|
|:---:|:---:|:---:|
|![Sketch](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-05-36.png)|![Body](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-06-34.png)|![3D](./Images/PU/Skærmbillede%20fra%202025-12-21%2010-06-46.png)|

#### Led SK6812_5050 RGBWW

|PCB|Led 5050|Glas|3D|
|:---:|:---:|:---:|:---:|
|![PU_Led_PCB](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-28-14.png)|![PU_Led_Sketch001](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-28-46.png)|![PU_Led_Sketch002](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-29-07.png)|![PU_Led_3D](./Images/PU/Skærmbillede%20fra%202025-12-21%2008-29-33.png)|

* FreeCAD File:
  * [Pu.FCStd](./Pu.FCStd)
