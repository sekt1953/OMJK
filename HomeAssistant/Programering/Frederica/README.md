# Programering af Fredericia Station

## ESPHome Firmware for Frederica

* Se ESPHome for ESP32 Firmware:
  * [/fa-spibg_0.yaml](./../../../ESPHome/fa-spibg_0.yaml)
    * [./Includes/Fa/Fa-Spibd/.pcf8574_ids_fa.yaml](./../../../ESPHome/Includes/Fa/Fa-SpIBD/.pcf8574_ids_fa.yaml)
    * [./Includes/Fa/Fa-Spibd/.pcf8574_input_fa.yaml](./../../../ESPHome/Includes/Fa/Fa-SpIBD/.pcf8574_input_fa.yaml)
  * [/fa-cap-spil_0.yaml](./../../../ESPHome/fa-cap-spil_0.yaml)
    * [./Includes/Cap/Fa/Fa-Cap-SpIL_0/.pca9685_ids_cap_fa.yaml](./../../../ESPHome/Includes/Cap/Fa/Fa-Cap-SpIL_0/.pca9685_ids_cap_fa.yaml)
    * [/Includes/Cap/Fa/Fa-SpIL_0/.pca9685_light_cap_fa.yaml](./../../../ESPHome/Includes/Cap/Fa/Fa-Cap-SpIL_0/ESPHome/Includes/Cap/Fa/Fa-SpIL_0/.pca9685_light_cap_fa.yaml)
    * [./Includes/Cap/Fa/Fa-Cap-SpIL_0/.pca9685_output_cap_fa.yaml](./../../../ESPHome/Includes/Cap/Fa/Fa-Cap-SpIL_0/.pca9685_output_cap_fa.yaml)

## Fredericia Spor Isolations

![FredericiaSporIsolationsNummer.png](./Images/FredericiaSporIsolationsNummer.png)

### SporIsolations BlockDetection --> Entity_id

|SporIsolation|Name|Entity_id|Komentar|
|:---:|:---|:---|:---|
|38|Fredericia-Block-Detection|||
|39|Fredericia-Block-Detection|||
|40|Fredericia-Block-Detection||Spor1|
|41|Fredericia-Block-Detection 07|binary_sensor.fa-spibd_007|Spor2|
|42|Fredericia-Block-Detection||Spor3|
|43|Fredericia-Block-Detection 03|binary_sensor.fa-spibd_003|Spor3 Grøn Led|
|44|Fredericia-Block-Detection 04|binary_sensor.fa-spibd_004|Spor3 Rød Led|
|45|Fredericia-Block-Detection 05|binary_sensor.fa-spibd_005|Spor2 Grøn Led|
|46|Fredericia-Block-Detection 02|binary_sensor.fa-spibd_002|Spor2 Rød Led|
|47|Fredericia-Block-Detection 01|binary_sensor.fa-spibd_001|Spor1 Grøn Led|
|48|Fredericia-Block-Detection 00|binary_sensor.fa-spibd_000|Spor1 Rød Led|

### Cap-Fredericia-SporIsolation Light --> Entity_id

|Name|Light.Entity_id|Komentar|
|:---|:---|:---|
|Cap-Fa-Spil-43|light.cap_fa_spil_001|Fa-Spor3 Grøn|
|Cap-Fa-SpiL-44|light.cap_fa_spil_000|Fa-Spor3 Rød|
|Cap-Fa-SpiL-45|light.cap_fa_spil_003|Fa-Spor2 Grøn|
|Cap-Fa-SpiL-46|light.cap_fa_spil_002|Fa-Spor2 Rød|
|Cap-Fa-SpiL-47|light.cap_fa_spil_005|Fa-Spor1 Grøn|
|Cap-Fa-SpiL-48|light.cap_fa_spil_004|Fa-Spor1 Rød|

## Frederica SporIsolation LightGroup --> Entity_id

### Group

|Name|Entity_id|Komentar|
|:---|:---|:---|
|Fa-Spilg-43|light.fa_spilg_43|Fa-Spor3 Grøn|
|Fa-Spilg-44|light.fa_spilg_44|Fa-Spor3 Rød|
|Fa-Spilg-45|light.fa_spilg_45|Fa-Spor2 Grøn|
|Fa-Spilg-46|light.fa_spilg_46|Fa-Spor2 Rød|
|Fa-Spilg-47|light.fa_spilg_47|Fa-Spor1 Grøn|
|Fa-Spilg-48|light.fa_spilg_48|Fa-Spor1 Rød|

### Group Options Members

|Group|Members Name|Members Entity_id|Komentar|
|:---|:---|:---|:---|
|Fa-Spilg-43|Cap-Fa-SpiL-43|light.cap_fa_001|Fa-Spor3 Grøn|
|||light.xx||
|Fa-Spilg-44|Cap-Fa-SpiL-44|light.cap_fa_000|Fa-Spor3 Rød|
|||light.xx||
|Fa-Spilg-45|Cap-Fa-SpiL-45|light.cap_fa_003|Fa-Spor2 Grøn|
|||light.xx||
|Fa-Spilg-46|Cap-Fa-SpiL-46|light.cap_fa_002|Fa-Spor2 Rød|
|||light.xx||
|Fa-Spilg-47|Cap-Fa-SpiL-47|light.cap_fa_005|Fa-Spor1 Grøn|
|||light.xx||
|Fa-Spilg-48|Cap-Fa-SpiL-48|light.cap_fa_004|Fa-Spor1 Rød|
|||light.xx||

## Automation Fa Block Detection (YAML)

Kilde: [YAML Style Guide](https://developers.home-assistant.io/docs/documenting/yaml-style-guide/)

### Alias & Description

```yaml
alias: Fa-BD
description: Markering af hvornår toget når til enden af sporet.
```

### When (Trigger)

#### Trigger

```yaml
trigger:
```

#### Trigger Spor1

```yaml
  - alias: Fa Spor1 SPI47 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_01
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-grøn-on
    trigger: state
  - alias: Fa Spor1 SPI47 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_01
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-grøn-off
    trigger: state
  - alias: FA Spor1 SPI48 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_00
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-rød-on
    trigger: state
  - alias: Fa Spor1 SPI48 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_00
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-rød-off
    trigger: state
```

#### Trigger Spor2

```yaml
  - alias: Fa Spor2 SPI45 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_05
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor2-grøn-on
    trigger: state
  - alias: Fa Spor2 SPI45 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_05
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor2-grøn-off
    trigger: state
  - alias: Fa Spor2 SPI46 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_02
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor2-rød-on
    trigger: state
  - alias: Fa Spor2 SPI46 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_02
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor2-rød-off
    trigger: state
```

#### Trigger Spor3

```yaml
  - alias: Fa Spor3 SPI43 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_03
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor3-grøn-on
    trigger: state
  - alias: Fa Spor3 SPI43 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_03
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor3-grøn-off
    trigger: state
  - alias: Fa Spor3 SPI44 ændret til besat
    entity_id:
      - binary_sensor.fa_spibd_0_04
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor3-rød-on
    trigger: state
  - alias: Fa Spor3 SPI44 ændret til fri
    entity_id:
      - binary_sensor.fa_spibd_0_04
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor3-rød-off
    trigger: state
```
### And if

```yaml
condition:
```

### Then to

#### [action & choose](https://www.home-assistant.io/docs/automation/action/)

```yaml
actions:
  - choose:
```

#### Spor1

```yaml
      - conditions:
          - alias: Når Fa Spor1 SPI47 ændret til besat
            condition: trigger
            id:
              - fa-spor1-grøn-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_47
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-grøn-off
            alias: Når Fa Spor1 SPI47 ændret til fri
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_47
      - conditions:
          - alias: Når FA Spor1 SPI48 ændret til besat
            condition: trigger
            id:
              - fa-spor1-rød-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_48
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_47
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-rød-off
            alias: Når Fa Spor1 SPI48 ændret til fri
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_48
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_47
```

#### Spor2

```yaml
      - conditions:
          - alias: Når Fa Spor2 SPI45 ændret til besat
            condition: trigger
            id:
              - fa-spor2-grøn-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_45
      - conditions:
          - alias: Når Fa Spor2 SPI45 ændret til fri
            condition: trigger
            id:
              - fa-spor2-grøn-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_45
      - conditions:
          - alias: Når FA Spor2 SPI46 ændret til besat
            condition: trigger
            id:
              - fa-spor2-rød-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_46
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_45
      - conditions:
          - alias: Når Fa Spor2 SPI46 ændret til fri
            condition: trigger
            id:
              - fa-spor2-rød-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_46
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_45
```

#### Spor3

```yaml
      - conditions:
          - alias: Når Fa Spor3 SPI43 ændret til besat
            condition: trigger
            id:
              - fa-spor3-grøn-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_43
      - conditions:
          - alias: Når Fa Spor3 SPI43 ændret til fri
            condition: trigger
            id:
              - fa-spor3-grøn-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_43
      - conditions:
          - alias: Når FA Spor3 SPI44 ændret til besat
            condition: trigger
            id:
              - fa-spor3-rød-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_44
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_43
      - conditions:
          - alias: Når Fa Spor3 SPI44 ændret til fri
            condition: trigger
            id:
              - fa-spor3-rød-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data: {}
            target:
              entity_id: light.fa_spilg_44
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spilg_43
```

[### Mode](https://www.home-assistant.io/docs/automation/modes/)

```yaml
mode: queued
max: 12
```
