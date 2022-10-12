This home assistant tcp sensor is a copy of already available 
[TCP Sensor](https://www.home-assistant.io/integrations/tcp/) with bytearray transmission support. More see pull request https://github.com/home-assistant/core/pull/80085

## Installation of the custom component

* Add custom repository https://github.com/se3/tcpsensor as Integration in HACS menu
* Follow the instruction https://hacs.xyz/docs/navigation/stores

* Enable the new sensor in your ```configuration.yaml```, see Description below
* Restart Home Assistant

### Configuration Example
```
sensor:
  - platform: tcp
    name: "TCP sensor name"
    host: 192.168.178.111
    port: 8899
    timeout: 10
    payload: "10 00 FF FF B6 00 00 00 C4"
    payload_is_hex: true
    value_template: "{{ value }}"
```

### Description
**payload_is_hex** (default: false) flag is optional, so all existing configurations are compatible to existing [TCP Sensor](https://www.home-assistant.io/integrations/tcp/) and handled same way.

payload and value format is a HEX string with space separator for better readability. see [byteaaray.fromhex](https://docs.python.org/dev/library/stdtypes.html#bytearray.fromhex) for more information.
