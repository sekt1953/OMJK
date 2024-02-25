# Home Assistant

## Kilder

* [Home Assistant](https://www.home-assistant.io/)
* [Github](https://github.com/)
  * [Creating an account on GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
  * [Getting started with your GitHub account](https://docs.github.com/en/get-started/onboarding/getting-started-with-your-github-account)

* [HACS, Home Assistant Community Store](https://github.com/hacs)
  * [Install HACS 2024](https://youtu.be/lhm4y3Gqol4 "Think Smart Home")
  * [Home Assistant Custom Cards | Best Custom Cards](https://youtu.be/96TTQJ7quMY?list=PLoo1sJ3CkxD0wyLcX4nG2_lm5GQNC1HvK "Anas Box")
* [Cloudflare Tunnels](https://www.cloudflare.com/)
  * [How to access Home Assistant remotely](https://youtu.be/DtIGEdwFtAk "Think Smart Home")
  * [Cloudflare Tunnels Setup on Synology NAS](https://youtu.be/QfffjK1e9ps "Think Smart Home")

## Setup

### Hardware

* In order not to spend a lot of money on hardware in the phase where I prove my ideas work, we use an older PC with an Intel I3 processor for our Home Assistant, we use another similar PC for OPNsense, and an older HP Switch with VLAN & PoE option to distubuate our network.

### Software

* [OPNsense](https://opnsense.org/download/)
* [Creating an account on GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
  * [Getting started with your GitHub account](https://docs.github.com/en/get-started/onboarding/getting-started-with-your-github-account)
* [INSTALL HOME ASSISTANT ON X86-64 MACHINES](https://www.home-assistant.io/installation/generic-x86-64)
  * Devices & services
    * [HACS, Home Assistant Community Store](https://github.com/hacs)
      * [simple-clock-card](https://github.com/arjhun/Homeassistant-Lovelace-Cards/tree/master/simple-clock-card)
      * [Button Card by @RomRider](https://github.com/custom-cards/button-card)
      * [Floorplan for Home Assistant](https://experiencelovelace.github.io/ha-floorplan/)
  * Add-ons
    * Advanced SSH & Web Terminal
    * ESPHome
    * File editor
    * MariaDB
    * Samba share
    * Studio Code Server
* [Cloudflare Tunnels](https://www.cloudflare.com/)

### Configuration

#### File structure

* /CONFIG
  * /blueprints
    * /automation
      * /train
        * /block_occupied_sensor.yaml
    * /script
  * /custom_components
    * /hacs
  * /esphome
    * /secrets.yaml
  * /images
  * /train
    * /input_boolean
      * /track_reserved.yaml
  * /tts
  * /www
    * /community
      * /ha-florplan
      * /simple-clock-card
    * /trainplan
      * /frederica
        * /frederica.css
        * /frederica.svg
      * /holmstrup
        * /holmstrup.css
        * /holmstrup.svg
  * /automations.yaml
  * /configuration.yaml
  * /scenes.yaml
  * /scripts.yaml
  * /secrets.yaml


#### Files

* [configuration files](./configurationsfiles.md)
  * [/CONFIG/secrets.yaml](configurationsfiles.md#configsecretsyaml)
  * [/CONFIG/configuration.yaml](./configurationsfiles.md#configconfigurationyamlml)

## Blueprint

### /CONFIG/blueprints/automation/train/***block_occupied_sensor.yaml***

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

#### /CONFIG/automations.yaml

Train occupied sensor 00_00:

```yaml
- id: '1683045478482'
  alias: Train occupied sensor 00_00
  description: ''
  use_blueprint:
    path: train/train_occupied_sensor.yaml
    input:
      reserved_sensor: input_boolean.track_reserved_00_00
      occupied_sensor: binary_sensor.tracksensor_00_00
      green_light_target:
        entity_id: switch.trackdisplay_00_00
      red_light_target:
        entity_id: switch.trackdisplay_00_10
```

track_section_occupied:

```yaml
- id: '1704825729184'
  alias: track_section_occupied
  description: ''
  trigger:
  - platform: state
    entity_id:
    - input_boolean.track_reserved_00_00
    from:
    id: track joins status change
    alias: When track train road joins status change
  condition: []
  action:
  - choose:
    - conditions:
      - condition: trigger
        id:
        - track joins status change
      - condition: state
        entity_id: input_boolean.track_reserved_00_00
        state: 'on'
      sequence:
      - service: switch.turn_on
        metadata: {}
        data: {}
        target:
          entity_id:
          - switch.leddriver_02_00
      alias: Track join train-road
    - conditions:
      - condition: trigger
        id:
        - track joins status change
      - condition: state
        entity_id: input_boolean.track_reserved_00_00
        state: 'off'
      sequence:
      - service: switch.turn_off
        metadata: {}
        data: {}
        target:
          entity_id:
          - switch.leddriver_02_00
      alias: Track train-road emergency_dissolves
  mode: single
```

## Views

## Automations