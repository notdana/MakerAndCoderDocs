# Module Servo

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo/uiflow_block_servo_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x222222)
i = None

servo = module.get(module.SERVO)

import random

while True:
  i = random.randint(0, 180)
  servo.write_angle(0, i)
  servo.write_angle(1, i)
  servo.write_angle(2, i)
  servo.write_angle(3, i)
  servo.write_angle(4, i)
  servo.write_us(0, 600)
  print((str("Servo's Status") + str(i)))
  wait(0.5)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo/uiflow_block_servo_angle.svg">

```python
servo.write_angle(0, 180)
```

- Drive Servo Rotation Angle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo/uiflow_block_servo_write.svg">

```python
servo.write_us(0, 600)
```

- Drive servo pulse duration

