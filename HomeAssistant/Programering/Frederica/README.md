# Programering af Fredericia Station

## Fredericia Spor Isolations Nummer

![FredericiaSporIsolationsNummer.png](./Images/FredericiaSporIsolationsNummer.png)

### Spor Isolations Nummer -> entity_id

|Spor Isolation|BlockDetection entity_id|Spor|Komentar|
|---:|:---|:---:|:---:|
|38||||
|39||||
|40||||
|41|binary_sensor.fa_bd_00_47|Spor2||
|42|binary_sensor.fa_bd_00_xx|Spor3||
|43|binary_sensor.fa_bd_00_43|Spor3|Grøn Led|
|44|binary_sensor.fa_bd_00_44|Spor3|Rød Led|
|45|binary_sensor.fa_bd_00_45|Spor2|Grøn Led|
|46|binary_sensor.fa_bd_00_42|Spor2|Rød Led|
|47|binary_sensor.fa_bd_00_41|Spor1|Grøn Led|
|48|binary_sensor.fa_bd_00_40|Spor1|Rød Led|

## Cap Frederica Block Detections Light

### Light.Entity_id

|Spor|Led|Light.Entity_id|Komentar|
|:---:|:---|:---:|:---:|
|Spor1|Grøn|light.cap_fa_00_05||
|Spor1|Rød|light.cap_fa_00_04||
|Spor2|Grøn|light.cap_fa_00_03||
|Spor2|Rød|light.cap_fa_00_02||
|Spor3|Grøn|light.cap_fa_00_01||
|Spor3|Rød|light.cap_fa_00_00||

## Block Detections Light Group

### Group

|Entity_id|Area|Add label|
|:---|:---:|:---:|
|light.fa_spor1_bd_lg_41|Fa|Fa_Spor1|
|light.fa_spor1_bd_lg_40|Fa|Fa_Spor1|
|light.fa_spor2_bd_lg_47|Fa|Fa_Spor2|
|light.fa_spor2_bd_lg_45|Fa|Fa_Spor2|
|light.fa_spor2_bd_lg_42|Fa|Fa_Spor2|
|light.fa_spor3_bd_lg_43|Fa|Fa_Spor3|
|light.fa_spor3_bd_lg_44|Fa|Fa_Spor3|

### Group Options Members

|Group|Members Entity_id||
|:---:|:---|:---:|
|light.fa_spor1_bd_lg_41|light.cap_fa_00_05||
||light.xx||
|light.fa_spor2_bd_lg_40|light.cap_fa_00_04||
||light.xx||
|light.fa_spor3_bd_lg_45|light.cap_fa_00_03||
||light.xx||
|light.fa_spor1_bd_lg_42|light.cap_fa_00_02||
||light.xx||
|light.fa_spor2_bd_lg_43|light.cap_fa_00_01||
||light.xx||
|light.fa_spor3_bd_lg_44|light.cap_fa_00_00||
||light.xx||

## Automation Fa Block Detection (YAML)

Kilde: [YAML Style Guide](https://developers.home-assistant.io/docs/documenting/yaml-style-guide/)

### Alias & Description

```yaml
alias: Fa-BD
description: Markering af hvornår toget til enden af sporet.
```

### When (Trigger)

#### Trigger

```yaml
trigger:
```

#### Trigger Spor1

```yaml
  # Spor1
  - platform: state
    entity_id:
      - binary_sensor.fa_bd_00_41
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-grøn-on
  - platform: state
    entity_id:
      - binary_sensor.fa_bd_00_41
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-grøn-off
  - platform: state
    entity_id:
      - binary_sensor.fa_bd_00_40
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-rød-on
  - platform: state
    entity_id:
      - binary_sensor.fa_bd_00_40
    to: "off"
    for:
      hours: 0
      minutes: 0
      seconds: 0
    id: fa-spor1-rød-off
```

#### Trigger Spor2

```yaml

```

#### Trigger Spor3

```yaml

```

### And if

```yaml
condition:
```

### Then to

#### [action & choose](https://www.home-assistant.io/docs/automation/action/)

```yaml
action:
  - choose:
```

[#### conditions (spor1)](https://www.home-assistant.io/docs/automation/condition/)

```yaml
      # Spor1
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-grøn-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spor1_bd_lg_41
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-grøn-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data:{}
            target:
              entity_id: light.fa_spor1_bd_lg_41
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-rød-on
        sequence:
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spor1_bd_lg_40
          - action: light.turn_off
            metadata: {}
            data:{}
            target:
              entity_id: light.fa_spor1_bd_lg_41
      - conditions:
          - condition: trigger
            id:
              - fa-spor1-rød-off
        sequence:
          - action: light.turn_off
            metadata: {}
            data:{}
            target:
              entity_id: light.fa_spor1_bd_lg_40
          - action: light.turn_on
            metadata: {}
            data:
              brightness_pct: 40
            target:
              entity_id: light.fa_spor1_bd_lg_41
```

#### conditions (spor2)

```yaml

```

#### conditions (spor3)

```yaml

```

[### Mode](https://www.home-assistant.io/docs/automation/modes/)

```yaml
mode: queued
max: 10
```
