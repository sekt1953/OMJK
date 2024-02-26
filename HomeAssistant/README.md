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
    * [Advanced SSH & Web Terminal](https://github.com/hassio-addons/addon-ssh)
    * [ArgonOne Active Cooling](https://community.home-assistant.io/t/argon-one-v1v2-active-cooling-and-active-linear-cooling-addon/262598)
    * [ESPHome](https://esphome.io/)
    * [File editor](https://github.com/home-assistant/addons/tree/master/configurator)
    * [MariaDB](https://github.com/home-assistant/addons/tree/master/mariadb)
    * [Samba share](https://github.com/home-assistant/addons/tree/master/samba)
    * [Samba Backup](https://github.com/thomasmauerer/hassio-addons/tree/master/samba-backup)
    * [Studio Code Server](https://github.com/hassio-addons/addon-vscode)
    * [Cloudflare Tunnels](https://github.com/brenner-tobias/addon-cloudflared/)

### Configuration

#### File structure

```data
/CONFIG/
  blueprints/
    automation/
      train/
        block_occupied_sensor.yaml
    script/
  custom_components/
    hacs/
  esphome/
    secrets.yaml
  images/
  train/
    input_boolean/
      track_reserved.yaml
  tts/
  www/
    community/
      ha-florplan/
      simple-clock-card/
    trainplan/
      frederica/
        frederica.css
        frederica.svg
      holmstrup/
        holmstrup.css
        holmstrup.svg
  automations.yaml
  configuration.yaml
  scenes.yaml
  scripts.yaml
  secrets.yaml
```

#### [Basic Configuration](./BasicConfiguration.md)

* [Basic files](./BasicConfiguration.md)
  * [/CONFIG/secrets.yaml](./BasicConfiguration.md#secretsyaml)
  * [/CONFIG/configuration.yaml](./BasicConfiguration.md#configurationyaml)

## [Helpers](./Helpers.md)

* [/CONFIG/train/input_boolean/](./Helpers.md#configtraininput_boolean)
  * [track_reserved.yaml](./Helpers.md#track_reservedyaml)

## [Blueprint](./BluePrint.md)

* [/CONFIG/blueprints/automation/train/](./BluePrint.md#configblueprintsautomationtrain)
  * [block_occupied_sensor.yaml](./BluePrint.md#block_occupied_sensoryaml)

## [Automations](./Automations.md)

* [/CONFIG/automations.yaml](./Automations.md#automations)
  * [Train occupied sensor 00_00](./Automations.md#train-occupied-sensor-00_00)
  * [track_section_occupied](./Automations.md#track_section_occupied)

## [Dashboards](./Dashboards.md)

* [Views](./Dashboards.md#views)
  * [HOME](./Dashboards.md#home)
  * [PWM](./Dashboards.md#pwm-with-pca9685)
  * [LEDDRIVER](./Dashboards.md#leddriver)
  * [OCCUPIED](./Dashboards.md#occupied)
  * [Track Reserved](./Dashboards.md#track-reserved)

### Add-ons

#### Advanced SSH & Web Terminal

Remember to change: username & authorized_keys and no password, then it only the pc with the corect ssh key that have access, you can have more keys.

```code
username: hassio
password: ""
authorized_keys:
  - >-
    ssh-ed25519
    asdspaaspdadsasdasdfasdfasdfasdfafsdf/
    abekat@gmail.com
  - >-
    ssh-ed25519
    asdspaasdasdhjkghghjghjjghjkgukfafsdf/
    hunkat@gmail.com
sftp: false
compatibility_mode: false
allow_agent_forwarding: false
allow_remote_port_forwarding: false
allow_tcp_forwarding: false
```
