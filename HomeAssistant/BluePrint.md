# Blueprint

## /CONFIG/blueprints/automation/train/

### block_occupied_sensor.yaml

```yaml
blueprint:
  name: Train occupied sensor
  description: switches lights on and off in the track board, depending on whether there are trains on the line.
  domain: automation
  author: Svenn-Erik K. Thomsen
  input:
    reserved_sensor:
      name: train track reserved
      description: ""
      selector:
        entity:
          domain: input_boolean

    occupied_sensor:
      name: Occupied Sensor
      description: "Detector that gives a signal when the track is occupied"
      selector:
        entity:
          domain: binary_sensor
          device_class: occupancy

    green_light_target:
      name: Green_Light
      description: "Shows the track reserved as part of a train route"
      selector:
        target:
          entity:
            domain: switch
    red_light_target:
      name: Red_Light
      description: ""
      selector:
        target:
          entity:
            domain: switch

    unoccupied_wait:
      name: Wait Unoccupied track
      description: Time until the track appears unoccupied after a train has left the track.
      default: 0
      selector:
        number:
          min: 0
          max: 3000
          step: 100
          unit_of_measurement: milliseconds 

# If motion is detected within the delay,
# we restart the script.
mode: restart
max_exceeded: silent

trigger:
  - platform: state
    entity_id: !input reserved_sensor
    from: "off"
    to: "on"
    id: reserved
  - platform: state
    entity_id: !input reserved_sensor
    from: "on"
    to: "off"
    id: free
  - platform: state
    entity_id: !input occupied_sensor
    to: "on"
    id: occupied
  - platform: state
    entity_id: !input occupied_sensor
    to: "off"
    id: unoccupied

condition: []

action: 
  - choose:
    - alias: "Turn on the Green light track reserved"
      conditions: 
        - condition: trigger
          id: reserved
      sequence:
        - service: switch.turn_on
          target: !input green_light_target
    - alias: "Turn off the Green light track not reserved"
      conditions: 
        - condition: trigger
          id: free
      sequence:
        - service: switch.turn_off
          target: !input green_light_target
    - alias: "Turn on the Red light track occupied"
      conditions: 
        - condition: trigger
          id: occupied
      sequence:
        - service: switch.turn_on
          target: !input red_light_target
        - service: switch.turn_off
          target: !input green_light_target
    - alias: "Turn off the light track unoccupied"
      conditions: 
        - condition: trigger
          id: unoccupied
      sequence:
        - service: switch.turn_off
          target: !input red_light_target
        - service: input_boolean.turn_off
          target:
            entity_id: !input reserved_sensor
```
