# HVAC Generic Thermostat custom component for Home Assistant

A custom component for Home Assistant that let you to control heating and cooling from the same thermostat entity. Based on official Generic Thermostat Component and on community thread <a href="https://community.home-assistant.io/t/heat-cool-generic-thermostat/76443">#76443</a>

## INSTALLATION

Copy all files in ha_config_folder/custom_components/hvac_generic_thermostat/ folder

## SAMPLE CONFIGURATION

Define the component with:
```yaml
climate:
  - platform: hvac_generic_thermostat
    name: Heat Cool Generic Thermostat
    cooler: switch.cooler
    heater: switch.heater
    target_sensor: sensor.any_themp_sensor
    min_temp: 15
    max_temp: 35
    target_temp: 23.5
    cold_tolerance: 1.0
    hot_tolerance: 1.0
    away_temp: 35
    initial_operation_mode: "off"
    min_cycle_duration:
      seconds: 5
    keep_alive:
      minutes: 3
    precision: 0.1
 ```
Field | Value | Necessity | Comments
--- | --- | --- | ---
platform | 'heat_cool_generic_thermostat' | *Required* |
name | Heat Cool Generic Thermostat | Optional |
cooler |  | *Required* | Switch that will activate/deactivate the cooling system |
heater |  | *Required* | Switch that will activate/deactivate the heating system |
target_sensor |  | *Required* | Sensor of actual room temperature |
min_temp | 7 | Optional | Minimum thermostat temperature (default value: 7) |
max_temp | 35 | Optional | Maximum thermostat temperature (default value: 35) |
target_temp |  | Optional | Desired temperature for the room |
cold_tolerance | 0.3 | Optional | Tolerance for cooling mode (default value: 0.3) |
hot_tolerance | 0.3 | Optional | Tolerance for heating mode (default value: 0.3) |
away_temp |  | Optional | Desired temperature for away mode |
initial_operation_mode |  | Optional | Operating mode at startup |
