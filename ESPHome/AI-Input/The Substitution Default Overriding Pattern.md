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

* Strategy 2: Use Packages instead of Includes (Recommended)
  * The ESPHome Packages system is much more flexible than !include. When using packages, components defined later in your file will override or merge with components imported from the package.
  * Instead of conditionally including an entire file, include the base package and override the specific keys you want to change.
  * base_node.yaml (The Package):

```yaml
esphome:
  name: unnamed-device

web_server:
  port: 80
```

*
  * device.yaml (Your Main File):

```yaml
packages:
  remote_base: !include base_node.yaml

# If you want to change the name or disable/override the web_server port,
# simply redeclare it lower down. The last definition wins.
esphome:
  name: kitchen-light

web_server:
  port: 8080 # Overrides port 80 from the package
```

* Strategy 3: Automations Lambda if Statements
  * If your "if statement" logic is meant to execute based on sensor data, time, or boot status, do not handle it at the YAML structural level. Instead, use an ESPHome Automation Action block or a C++ lambda function inside your included code.

```yaml
# Inside your included YAML file
on_boot:
  then:
    - if:
        condition:
          lambda: 'return id(is_aquarium_device).state;'
        then:
          - logger.log: "Aquarium features enabled!"
        else:
          - logger.log: "Standard features enabled."
```

*
  * If you need help structuring this, could you share what specific setting you are trying to change conditionally and what triggers that condition?