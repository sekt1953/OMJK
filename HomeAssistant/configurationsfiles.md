# Confifurations files

## /CONFIG/secrets.yaml

```yaml
# Use this file to store secrets like usernames and passwords.
# Learn more at https://www.home-assistant.io/docs/configuration/secrets/
# some_password: welcome

# MariaDB mysql://user:password@SERVER_IP/DB_NAME?charset=utf8mb4
# Kilde: https://www.home-assistant.io/integrations/recorder/#custom-database-engines
maria_db: mysql://user:password@core-mariadb/DB_NAME?charset=utf8mb4
```

## /CONFIG//configuration.yaml

```yaml
# Loads default set of integrations. Do not remove.
default_config:

# Text to speech
tts:
  - platform: google_translate

automation: !include automations.yaml
script: !include scripts.yaml
scene: !include scenes.yaml


input_boolean: !include_dir_merge_named ./train/input_boolean

recorder:
  db_url: !secret maria_db
```
