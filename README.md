# Ansible Role: `aisbergg.lm_sensors`

This Ansible role installs `lm-sensors` and detects available sensors on Debian, RedHat and ArchLinux systems.

## Requirements

None.

## Role Variables

| Variable | Default | Comments |
|----------|---------|----------|
| `lm_sensors_force_detection` | `false` | Force detection of sensors. By default the sensor detection is only performed upon installation. |
| `lm_sensors_configs` | `{}` | Dictionary of lm-sensors configurations. See example down below. |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  vars:
    lm_sensors_force_detection: true
    lm_sensors_configs:
      # create a config file '/etc/sensors.d/HP_Z600'
      HP_Z600: |
        chip "coretemp-isa-0000"
          label temp2 "Core 0"
          label temp3 "Core 1"
          label temp11 "Core 2"
          label temp12 "Core 3"

  roles:
    - aisbergg.lm_sensors
```

## License

MIT

## Author Information

Andre Lehmann (aisberg@posteo.de)
