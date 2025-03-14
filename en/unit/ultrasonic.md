# Unit Ultrasonic

## Example

Obtain Ultrasonic measurement data collected by ultrasonic

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ultrasonic/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
Ultrasonic_0 = unit.get(unit.ULTRASONIC, unit.PORTA)

while True:
  print(Ultrasonic_0.distance)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ultrasonic/uiflow_block_Ultrasonic_distance.svg">

```python
print(Ultrasonic_0.distance)
```

- Gets the ultrasonic measurement data collected by the device Sonic IO and returns a float type
