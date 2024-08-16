# PCB for ESPHome enheder

## Software

* Jeg bruger [Fritzing](https://fritzing.org/learning/) til at tegne mine print i.
  * En ældre version af Fritzing kommer med Ubuntu 22.04 og en nyere version kan købes online her: [https://fritzing.org/download/](https://fritzing.org/download/)
  * Fritzing findes i versioner for Windows, Mac og Linux, så det er bare at komme igang.
* Jeg bruger [FreeCAD](https://www.freecad.org/features.php?lang=en) til at tegne holdere for mine print.
  * FreeCAD er et gratis, og godt 3D-tegneprogram, det kan hentest her: [https://www.freecad.org/downloads.php?lang=en](https://www.freecad.org/downloads.php?lang=en)
  * FreeCAD bruger vejledning kan findes her: [https://wiki.freecad.org/User_hub](https://wiki.freecad.org/User_hub)


## Print

Jeg bruger ofte et [stripboard](./Stripboard/README.md) til at bygge prototyper på, og mindre styk antal, skal jeg have fremstillet print bruger jeg [https://aisler.net/partners/fritzing](https://aisler.net/partners/fritzing), her kan jeg sende **fzz** filer til uden at skulle bekymre mig om **svg** filer, det er nemt.

* [CPU print](./CPU/README.md)
  * [Olimex ESP32-POE-ISO](./CPU/README.md#olimex-esp32-poe-iso-16mb)
  * [CPU ESP32-dev](./CPU/README.md#esp32-dev-30pin-med-i2c-interface)
* [I2C IO_Interface med PCF8574](./I2C%20IO_Interface/README.md)
* [I2C LEDDriverPWM med PCA9685](./LEDDriverPWM/README.md)
* [BlockDetection med NCE_BD20](./BlockDetection/README.md)
* [SporskifteDriver med TB6612FNG](./SporskifteDriver/README.md)
* [Stripboard](./Stripboard/README.md)
