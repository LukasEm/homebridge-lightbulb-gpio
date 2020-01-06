# Homebridge Relays

Controls 4 channel relays with a Raspberry Pi using HomeKit.

# Hardware

The hardware is quite simple to construct.

1. Any Raspberry Pi
2. Relay connected to light bulb and rpi gpio

# Installation

1. Install homebridge using: `npm install -g homebridge`
2. Install this plugin using: `npm install -g homebridge-lightbulb-gpio`
3. Update your configuration file. See `config-sample.json` in this repository for a sample.

# Sample Configuration

```json
{
  "accessories": [
    {
      "accessory": "LightBulbGpio",
      "name": "Living room light",
      "pin": 11
      "invert": false,
      "default_state": false
    }
  ],

  "platforms": []
}
```

# Accessory Configuration Options

Name             | Meaning
---------------- | ------------------------------------------------
`accessory`      | Accessory type. `Relay` (REQUIRED)
`name`           | Default name for the accessory. (REQUIRED)
`pin`            | Which pin number to use for this accessory. (REQUIRED)
`invert`         | If true, output on pin is `LOW` for `ON`, and `HIGH` for `OFF`. (Default: false)
`default_state` | State to set on start of homebridge.  `true` for `ON`, `false` for `OFF`. (Default: `false`/`OFF`)
`duration_ms`   | If given, accessory will stay ON for this many milliseconds, then turn OFF.  Timer resets if accessory is turned ON again while it is still ON. (Default: 0/None)


