# ESP MQTT Dimmer
Control MOSFETs over MQTT to dim LEDs.

## Libs
PubSubClient

## Protocol

### Pin
> Sets given pins to given values.

On `/.../set`

Byte | Description
---- | -----------
1    | Number of pins to set
1    | #0 Pin to use
1    | #0 Brightness (0-255)
1    | #1 Pin to use
1    | #1 Brightness (0-255)
...  | ...

Device send confirmation on `/.../didSet` with the same value. So we can
confirm on the controller that the Device did set the value.



### Keepalive
> To monitor which devices is running

On `/.../alive` the device send confirmation on `/.../isAlive` with `OK`



### Sleep
> The controller can tell the device to put itself to sleep mode, e.g. at night
> to reduce power consumption.

On `/.../sleep`

Byte | Description
---- | -----------
2    | Seconds to sleep

The device asks for it with `/.../getSleep`.



### 433 Recever
If we have no Wifi, it should be still possible to control the Device, on and
off will be enough.
