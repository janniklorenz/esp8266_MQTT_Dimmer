# ESP MQTT Dimmer
Control MOSFETs over MQTT to dim LEDs.

## Libs
PubSubClient

## Protocol

### Pin
> Sets given pins to given values.

On `/.../set`

````json
[
	{pin: 13, value: 0},
	{pin: 15, value: 100}
]
````

Device send confirmation on `/.../didSet` with the same value. So we can
confirm on the controller that the Device did set the value.



### Keepalive (TODO)
> To monitor which devices is running

On `/.../alive` the device send confirmation on `/.../isAlive` with `OK`



### Sleep (TODO)
> The controller can tell the device to put itself to sleep mode, e.g. at night
> to reduce power consumption.

On `/.../sleep`



### 433 Recever (TODO)
If we have no Wifi, it should be still possible to control the Device, on and
off will be enough.
