# ESPHome

## Setup

### Configuration

#### File structure

```data
/CONFIG/
  esphome/
    secrets.yaml
```

#### Basic Configuration

``ỳaml

```

* [ESPHome](./esphome.md)
* [ESPHome files:](./esphome.md)
  * ESPHome's Secrets Files:
    * [secrets.yaml](./esphome.md#secretsyaml)
  * Leddriver Files:
    * ESPHome files:
      * [leddriver-xx.yaml](./leddriver-xx.yaml)
    * Fritzing Files;
      * [PCB-LedDriver-V6.1.fzz](https://github.com/sekt1953/Fritzing/blob/main/My_PCB/LedDriver/v6.1/PCB-LedDriver-V6.1.fzz)
    * FreeCAD Files:
      * [LedDriverv6.1a.FCStd](https://github.com/sekt1953/FreeCAD/blob/main/LeadDriverv6.1/LedDriverv6.1a.FCStd)
  * OccupiedSensor Files:
    * ESPHome Files:
      * [occupied-xx.yaml](./occupied-xx.yaml)
      * [Occupied-Hp.yaml "Holmstrup"](./Occupied-Hp.yaml)
    * Fritzing Files:
      * [occupied_sensor](https://github.com/sekt1953/Fritzing/blob/main/My_PCB/README.md#occupied_sensor-work-in-progress)
  * PWM with pca9685
    * ![PCA9685](./Images/Skærmbillede%20fra%202024-01-23%2013-13-27.png)
    * ESPHome Files:
      * [/pca9685-xx.yaml](./pca9685-00.yaml)
    * FreeCAD files:
      * [Mount for PCA9685 PCB](https://github.com/sekt1953/FreeCAD#mount-for-pca9685-pcb)
