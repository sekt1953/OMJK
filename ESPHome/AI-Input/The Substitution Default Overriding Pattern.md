# The Substitution Default Overriding Pattern

* ESPHome does not support native if statements:
  * ESPHome does not support native if statements or conditional logic inside a YAML !include statement. Because YAML is purely a static descriptive language and lacks a built-in preprocessor engine,
  * ***you cannot write an expression like !include ${ 'wifi.yaml' if status else 'ethernet.yaml' }***
* Strategy 1: The Substitution Default Overriding Pattern
  * Instead of choosing which file to include, include a template file that relies on ESPHome Substitutions. You can define blank or default behaviors that you override only when needed.
  * common_wifi.yaml (The Included File):

```yaml  
wifi:
  ssid: "MyHomeWiFi"
  password: "SecretPassword"
  # If $fast_connect is text-replaced with 'fast_connect: true', it enables it.
  # If left as an empty comment placeholder, it does nothing.
  $fast_connect_setting 
```
* 
  * device.yaml (Your Main File):

```yaml  
substitutions:
  # Overrides the blank placeholder with valid YAML config
  fast_connect_setting: "fast_connect: true" 

<<: !include common_wifi.yaml
```
