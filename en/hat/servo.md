# Hat Servo

## Example

> Rotates the servo to different positions every second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/servo/uiflow_block_hat_servo_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_servo_0 = hat.get(hat.SERVO)

while True:
  hat_servo_0.write_angle(0)
  wait(1)
  hat_servo_0.write_angle(90)
  wait(1)
  hat_servo_0.write_angle(180)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/servo/uiflow_block_servo_hat_angle.svg">

```python
hat_servo_0.write_angle(0)
```

- This block sets the servo to a specified angle (in degrees). In this example, it’s set to 0 degrees.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/servo/uiflow_block_servo_hat_write.svg">

```python
hat_servo_0.write_us(600)
```

- This block writes a pulse width directly to the servo in microseconds. In this example, it’s set to a 600-microsecond pulse width.