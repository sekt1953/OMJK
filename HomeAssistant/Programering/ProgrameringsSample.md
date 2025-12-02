# programmerings eksempler, løsninger fundet på nettet

* Eksempler:
    * [can't get response_variable by calling a script](./ProgrameringsSample.md#cant-get-response_variable-by-calling-a-script)

## can't get response_variable by calling a script

* Kilder:
  * [DanPuz](https://www.reddit.com/user/DanPuz/)
    * [cant_get_response_variable_by_calling_a_script](https://www.reddit.com/r/homeassistant/comments/1guu77r/cant_get_response_variable_by_calling_a_script/)

### Call Random Generator

```yaml
alias: Call Random Generator
description: ""
triggers:
  - trigger: state
    entity_id:
      - binary_sensor.ju_udvendig_betjeningsskab_00
    from: "off"
    to: "on"
    id: 101+
    variables:
      motor_off:
        - switch.ju_sp_tp_101a1
        - switch.ju_sp_tp_101a2
      motor_on:
        - switch.ju_sp_tp_101a2
      sporskifte_sensor_on: binary_sensor.ju_sp_tp_28
conditions: []
actions:
  - action: script.random_generator
    metadata: {}
    data: {}
    response_variable: result
  - action: notify.persistent_notification
    metadata: {}
    data:
      message: "{{ result.value }}"
```

### random generator

```yaml
alias: random generator
description: ""
variables:
  value: >
    {{ { 'value0': range(1, 99) | random , 'value1': range(100, 199) | random } }}
sequence:
  - stop: returning value
    response_variable: value
```
