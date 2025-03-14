# Hat Puppyc

## Example

> Changes the angle of all servos every second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/puppyc/uiflow_block_hat_puppyc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_puppyC_0 = hat.get(hat.PUPPY)

while True:
  hat_puppyC_0.SetAllAngle(0, 90, 180, 0)
  wait(1)
  hat_puppyC_0.SetAllAngle(90, 180, 0, 90)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/puppyc/uiflow_block_hat_puppy_all_angle.svg">

```python
hat_puppyC_0.SetAllAngle(0, 0, 0, 0)
```

- Sets the angle of multiple servos simultaneously, from servo 0 to 3, where each value represents the rotation angle for each servo.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/puppyc/uiflow_block_hat_puppy_angle.svg">

```python
hat_puppyC_0.SetAngle(0, 0)
```

- Sets the rotation angle of a specific servo. You can specify the servo number and set its rotation angle.