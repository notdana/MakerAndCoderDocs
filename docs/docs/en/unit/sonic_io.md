# Unit Ultrasonic-IO


## Example

Obtain Sonic IO measurement data collected by ultrasonic

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/sonicio/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
Ultrasonic_0 = unit.get(unit.ULTRASONIC, unit.PORTA)
sonic_io_0 = unit.get(unit.SONIC_IO, unit.PORTB)

while True:
  print(sonic_io_0.get_distance(1))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/sonicio/uiflow_block_sonic_io_get_distance.svg">

```python
print(sonic_io_0.get_distance(1))
```

- Gets the Senic IO measurement data collected by the device Sonic IO and returns a float type
