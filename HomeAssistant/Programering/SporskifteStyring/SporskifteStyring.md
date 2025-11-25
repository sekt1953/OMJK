# Sporskifte Styring

!! Advarsel work in progress 2025-11-25 15:30

## Kilder

* [Using Response variable in a script](https://community.home-assistant.io/t/using-response-variable-in-a-script/738730)
* Mine link:
  * [https://github.com/sekt1953/HomeAssistant/Programering/SporskifteStyring](https://github.com/sekt1953/OMJK/tree/main/HomeAssistant/Programering/SporskifteStyring "This Scripts")
  * [Tortoise Slow-Motion Switch Machine](./../../../DataSheet/800-6000ins.pdf)
    * ![Tortoise Slow-Motion Switch Machine](./Images/Skærmbillede%20fra%202025-11-25%2019-10-24.png)
  * [Sporskifte Driver med TB6612FNG for Tortoise Point Motors](./../../../ESPHome/PCB/README.md)

## Helpers Light_Groups

* Transversal_101_Light
  * Retning
    * Plus :
    * Minus :
  * Sporskifte_101a
    * Låst:
  * Sporskifte_101b
    * Låst:

## Automations

### Start_Blink.yaml

```yaml
alias: Start Blink
description: ""
triggers:
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_07
    from: "off"
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 0.1
conditions: []
actions:
  - action: script.blink
    data: {}
mode: single
```

### Ju_UdvendigBetjening.yaml

```yaml
alias: Ju_UdvendigBetjening
description: ""
triggers:
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_00
    from: "off"
    to: "on"
    id: 101+
    variables:
      led_off:
        - light.ju_udvendig_betjeningsskab_section_01
        - light.ju_udvendig_betjeningsskab_section_02
        - light.ju_udvendig_betjeningsskab_section_03
      led_on:
        - light.ju_udvendig_betjeningsskab_section_01
        - light.ju_udvendig_betjeningsskab_section_03
      motor_a_off:
        - switch.ju_sp_tp_101a1
        - switch.ju_sp_tp_101a2
      motor_b_off:
        - switch.ju_sp_tp_101b2
        - switch.ju_sp_tp_101b1
      motor_on_a:
        - switch.ju_sp_tp_101a2
      motor_on_b:
        - switch.ju_sp_tp_101b1
      sporskifte_a_sensor_on: binary_sensor.ju_sp_tp_28
      sporskifte_a_sensor_off: binary_sensor.ju_sp_tp_2a
      sporskifte_b_sensor_on: binary_sensor.ju_sp_tp_2c
      sporskifte_b_sensor_off: binary_sensor.ju_sp_tp_2e
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_02
    from: "off"
    to: "on"
    id: 101-
    variables:
      led_off:
        - light.ju_udvendig_betjeningsskab_section_01
        - light.ju_udvendig_betjeningsskab_section_02
        - light.ju_udvendig_betjeningsskab_section_03
      led_on:
        - light.ju_udvendig_betjeningsskab_section_02
      motor_a_off:
        - switch.ju_sp_tp_101a1
        - switch.ju_sp_tp_101a2
      motor_b_off:
        - switch.ju_sp_tp_101b2
        - switch.ju_sp_tp_101b1
      motor_on_a:
        - switch.ju_sp_tp_101a1
      motor_on_b:
        - switch.ju_sp_tp_101b2
      sporskifte_a_sensor_on: binary_sensor.ju_sp_tp_2a
      sporskifte_a_sensor_off: binary_sensor.ju_sp_tp_28
      sporskifte_b_sensor_on: binary_sensor.ju_sp_tp_2e
      sporskifte_b_sensor_off: binary_sensor.ju_sp_tp_2c
conditions: []
actions:
  - action: script.skifttransversal
    data:
      trigger_entity: "{{ trigger.entity_id }}"
      motor_on_a: "{{ motor_on_a }}"
      motor_on_b: "{{ motor_on_b }}"
      led_off: "{{ led_off }}"
      led_on: "{{ led_on }}"
      motor_a_off: "{{ motor_a_off }}"
      motor_b_off: "{{ motor_b_off }}"
      sporskifte_a_sensor_on: "{{ sporskifte_a_sensor_on }}"
      sporskifte_a_sensor_off: "{{ sporskifte_a_sensor_off }}"
      sporskifte_b_sensor_on: "{{ sporskifte_b_sensor_on }}"
      sporskifte_b_sensor_off: "{{ sporskifte_b_sensor_off }}"
mode: single
variables:
  led_off: ""
  led_blink: ""
  led_on: ""
  motor_a_off: ""
  motor_b_off: ""
  motor_on_a: ""
  motor_on_b: ""
  sporskifte_a_sensor_on: ""
  sporskifte_a_sensor_off: ""
  sporskifte_b_sensor_on: ""
  sporskifte_b_sensor_off: ""
```

## Scripts

### Blink.yaml

```yaml
alias: Blink
description: "Blink Program for testing with blink"
sequence:
  - repeat:
      until:
        - condition: state
          entity_id: binary_sensor.ju_udvendig_betjeningsskab_0f
          state: "on"
          for:
            hours: 0
            minutes: 0
            seconds: 1
      sequence:
        - action: homeassistant.turn_on
          metadata: {}
          data:
            transition: 0
            color_temp_kelvin: 3500
            brightness_pct: 40
          target:
            entity_id: group.synkron_led_blink
        - delay:
            hours: 0
            minutes: 0
            seconds: 0
            milliseconds: 500
        - action: homeassistant.turn_off
          metadata: {}
          data:
            transition: 0
          target:
            entity_id: group.synkron_led_blink
        - delay:
            hours: 0
            minutes: 0
            seconds: 0
            milliseconds: 500
```

### Blink_Add_Light_Entities.yaml

* Entity ID: 
  * script.blink_add_entities

```yaml
alias: Blink_Add_Light_Entities
description: "Add Light_Entities to Blink"
sequence:
  - action: group.set
    metadata: {}
    data:
      object_id: synkron_led_blink
      add_entities: "{{ led_blink }}"
fields:
  led_blink:
    selector:
      text: null
    default: "{{ led_off }}"
```

### Blink_Remove_Light_Entities.yaml

* Entity ID: 
  * script.1759602452553

```yaml
alias: Blink_Remove_Light_Entities
description: "Remove Light_Entities from Blink"
sequence:
  - action: group.set
    metadata: {}
    data:
      object_id: synkron_led_blink
      remove_entities: "{{ led_blink }}"
  - action: light.turn_off
    metadata: {}
    data: {}
    target:
      entity_id: "{{ led_blink }}"
fields:
  led_blink:
    selector:
      text: null
    default: "{{ led_off }}"
```

### SkiftEtSporskifte.yaml

```yaml
alias: SkiftEtSporskifte
description: >-
  Ændre et sporskifte indstilling, 
    return 'Ok' on success and 'TimeOut' on failure.
sequence:
  - action: switch.turn_off
    metadata: {}
    data: {}
    target:
      entity_id: "{{ motor_off }}"
  - action: switch.turn_on
    metadata: {}
    data: {}
    target:
      entity_id: "{{ motor_on }}"
  - wait_template: "{{ is_state(sporskifte_sensor_on,'on') }}"
    continue_on_timeout: true
    timeout: "00:00:20"
  - if:
      - condition: template
        value_template: "{{ wait.completed }}"
    then:
      - stop: SkiftEtSporskifte Ok
        response_variable: "Ok"
    else:
      - stop: SkiftEtSporskifte TimeOut
        response_variable: "TimeOut"
fields:
  motor_off:
    selector:
      text: null
    default: "{{ motor_off }}"
    name: motor_off
    required: true
  motor_on:
    selector:
      text: null
    default: "{{ motor_on }}"
    name: motor_on
    required: true
  sporskifte_sensor_on:
    selector:
      text: null
    default: "{{ sporskifte_sensor_on }}"
    name: sporskifte_sensor_on
    required: true
```

### SkiftTransversal.yaml

```yaml
alias: SkiftTransversal
description: ""
sequence:
  - action: script.1759602452553
    metadata: {}
    data:
      led_blink: "{{ led_off }}"
  - action: light.turn_off
    metadata: {}
    data:
      transition: 0
    target:
      entity_id: "{{ led_off }}"
  - action: switch.turn_off
    metadata: {}
    data: {}
    target:
      entity_id: "{{ motor_a_off }}"
  - action: switch.turn_off
    metadata: {}
    data: {}
    target:
      entity_id: "{{ motor_b_off }}"
  - wait_template: "{{ is_state(trigger_entity,'off') }}"
    continue_on_timeout: true
    timeout: "00:00:00.700"
  - if:
      - condition: template
        value_template: "{{ not wait.completed }}"
    then:
      - sequence:
          - action: script.blink_add_entities
            metadata: {}
            data:
              led_blink: "{{ led_off }}"
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id: "{{ motor_on_a }}"
          - wait_template: "{{ is_state(sporskifte_a_sensor_on,'on') }}"
            continue_on_timeout: false
            enabled: true
            timeout: "00:00:20"
          - if:
              - condition: template
                value_template: "\"{{ wait.completed }}\""
            then:
              - sequence:
                  - action: script.1759602452553
                    metadata: {}
                    data:
                      led_blink: "{{ led_off }}"
                  - action: light.turn_off
                    metadata: {}
                    data:
                      transition: 0
                    target:
                      entity_id: "{{ led_off }}"
                  - stop: ""
          - action: switch.turn_on
            metadata: {}
            data: {}
            target:
              entity_id: "{{ motor_on_b }}"
          - wait_template: "{{ is_state(sporskifte_b_sensor_on,'on') }}"
            continue_on_timeout: true
            enabled: true
            timeout: "00:00:20"
          - if:
              - condition: template
                value_template: "\"{{ wait.completed }}\""
            then:
              - sequence:
                  - action: script.1759602452553
                    metadata: {}
                    data:
                      led_blink: "{{ led_off }}"
                  - action: light.turn_off
                    metadata: {}
                    data:
                      transition: 0
                    target:
                      entity_id: "{{ led_off }}"
          - action: script.1759602452553
            metadata: {}
            data:
              led_blink: "{{ led_off }}"
          - action: light.turn_on
            metadata: {}
            data:
              transition: 0
            target:
              entity_id: "{{ led_on }}"
    else:
      - sequence:
          - action: persistent_notification.create
            metadata: {}
            data:
              message: "{{ trigger_entity }} {{ wait.remaining }}"
              title: Else
            enabled: false
          - stop: Tryk for kortvarig
            enabled: false
          - action: script.1759602452553
            metadata: {}
            data:
              led_blink: "{{ led_off }}"
            enabled: false
fields:
  led_off:
    selector:
      text: null
    default: "{{ led_off }}"
    required: true
  led_on:
    selector:
      text: null
    name: led_on
    default: "{{ led_on }}"
    required: true
  motor_a_off:
    selector:
      text: null
    default: "{{ motor_a_off }}"
    required: true
  motor_b_off:
    selector:
      text: null
    default: "{{ motor_b_off }}"
    required: true
  motor_on_a:
    selector:
      text: null
    default: "{{ motor_on_a }}"
    required: true
  motor_on_b:
    selector:
      text: null
    default: "{{ motor_on_a }}"
    required: true
  sporskifte_a_sensor_on:
    selector:
      object: {}
    default:
      "[object Object]": null
  sporskifte_a_sensor_off:
    selector:
      text: {}
    default: "{{ sporskifte_a_sensor_off }}"
    required: true
  sporskifte_b_sensor_on:
    selector:
      text: null
    name: sporskifte_b_sensor_on
    required: true
  sporskifte_b_sensor_off:
    selector:
      text: null
    name: sporskifte_a_sensor_off
    required: true
  trigger_entity:
    selector:
      template: {}
    default: "{{ trigger_entity }}"
```
