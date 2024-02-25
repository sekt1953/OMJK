# Home Assistant as Railway Controler

## Why

* [Home Assistant](https://www.home-assistant.io/) can control many parts of my house, it can make sure the lights turn on when needed, it can control my lawnmower, it can check if someone is in the house, send an alarm if there is an unwanted visitor, so why don't use it to control our model railway, it's just some lights and some switches and a bit of logic.
* And not least, it is easy to program for non-programmers, and there is plenty of good documentation.
* To interface our model railway, [Home Assistant](https://www.home-assistant.io/) has built in [ESPHome](https://esphome.io/) which is an Arduino-like platform that allows us to use [ESP](https://esphome.io/components/esp32) & [Raspberry](https://esphome.io/components/rp2040) Microcontroller to interface with the model railway

### Step to get there

* to get a stable block detection to work, we must use block detection to feed our logic system.
* will be to be able to control our signals, since they will be our output from our logic system.
* will be to control our switches, as their position must be included in our logic system.
* other not know for now.

### Electronics building blocks

* I have spent half a year developing a set of building blocks like Lego bricks so we can use some standard components for the installation, all based on the [ESP](https://esphome.io/components/esp32) MCU and [ESPHome](https://esphome.io/).
* The first module is a Binary Input/Output with [PCF8574](https://www.nxp.com/docs/en/data-sheet/PCF8574_PCF8574A.pdf), connected to ESP32 via I2C interface, with it we will connect Block Detection modules to Home Assistant.
* To control our LEDs in signals and desks, I have been a long way around control via optocouplers, in order to be able to connect to already set up equipment, but found a small smart print with a [PCA9685](https://www.nxp.com/products/power-management/lighting-driver-and-controller-ics/led-controllers/16-channel-12-bit-pwm-fm-plus-ic-bus-led-controller:PCA9685) chip which has [PWM](https://da.wikipedia.org/wiki/Pulsbreddemodulation) output and [I2C](https://www.ti.com/lit/an/sbaa565/sbaa565.pdf?ts=1708812930096&ref_url=https%253A%252F%252Fwww.google.com.ar%252F) interface for [ESP](https://esphome.io/components/esp32) MCU.
* Driver for [LED Strip RGBWW V-TAC VT-505-60](https://www.ledproff.dk/12v-rgb-ledstrips/250-v-tac-108w-m-rgb-staenktaet-led-strip-5m-60-led-pr-meter-3800157676281.html), a desire has arisen to be able to control the lighting in the room when we drive according to the timetable, a strip of LED Strip has been purchased for this, so the next m´building block for our electronics is a drive that can interface with our Binary Input/Output module.

### Test and show progress

* I find the best way to see if something works is to show it in Home Assistant Views.
* it gives a quick overview of whether Block Detection works as desired, we can with the Home Assistant Companion App on our phone, follow our model train around the facility and get a visual information.
* In the same way, we can use another view to find and switch off Led in desks and signals, and thus get confirmation that the installation is in order.

## Home Assistant

* Setup
* Views
* Automations

## ESPHome

* ESP32 MCU
  * I2C_ IO_Interface with PCF8574
    * Block Detecsion with BD20 interface
    * Block Detecsion with 12 Diode Interface
  * Led Driver with PCA9685
    * Led Strip Driver ULN2803A & IRLZ44

## DataBase Project

* [DataBase Project]()
  * [Database server installation]()
  * [Creating Database in LibreOffice]()
