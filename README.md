# CREATE IKOHS Windcalm DC ceiling fan
Create (IKOHS) Windcalm DC convert white ceiling fan (with remote and wireless)

After installing the ceiling fan, which was fairly easy I performed the wireless configuration and soon found the wireless implementation is based on Tuya.

The fan is well balanced, very stable, and doesn't make any sound apart from the wind it moves.
This fan is fitted with a LED panel, brightness can be adjusted, and allows three color modes (warm, warm-white, and white).
The remote control operates wireless (I have not gathered any specs).
Wireless only supports 2.4GHz.

# Major disappointment: state not updated
The state does not match/ is not updated when remote, and app (wireless) are both used. For example, if you turn on the fan using the CREATE app (or any Tuya compatible app) and you turn off the fan using the remote control the state is not updated, and the app still asumes the fan is turned on. The broadcasted messages (with state information) by the fan confirms this.

Most equipment around the house is operated and automated using Home-Assistant. The fan not reporting the correct state if the remote control is also used is not workable. 

# Disappointment: Light too bright and warm light could be warmer
We have installed the fan in the master bedroom, and the minimum brightness level is too bright. The warm color mode is not warm enough which I expected the color temperature to be around 2400K. If I guess the warm color temperature is around 3500K and white 6000K (Kelvin).

# Too bad: the beep cannot be disabled
Every action is acknowlegded with a short, soft beep which is annoying and cannot be disabled.

# Overview of DPS

Sample broadcast message:
```
DPS: {'20': False, '23': 0, '60': False, '62': 1, '63': 'forward', '64': 0}
```

Key value mappings:
 - key: 20 is used for the light if `False` the light is off and if `True` the light is on
 - key: 22 is used for the light brightness, value between `0` and `1000`
 - key: 23 is used for the light color temperature if `0` the light is warm, if `500` the light is Warm-White and if `1000` the light is White
 - key: 60 is used for the fan if `False` the fan is off and if `True` the fan is on
 - key: 62 is used for speed control, value between `1` and `6`
 - key: 63 is used for fan rotation direction, values are `forward` or `reverse`
 - key: 64 is unknown


What tools I used and how I added the fan to home-assistant to be continued.

Good places to start are:
https://github.com/rospogrigio/localtuya
