# Hat 8Servo

## Example

> Control multiple servos to rotate at specific angles every second in a loop. You can continue to add more servos if needed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo/uiflow_block_8servo_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_servos_1 = hat.get(hat.SERVOS)

hat_servos_1.SetAngle(1, 0)
hat_servos_1.SetAngle(2, 0)
hat_servos_1.SetAngle(3, 0)
hat_servos_1.SetAngle(4, 0)
wait(1)
hat_servos_1.SetAngle(1, 90)
hat_servos_1.SetAngle(2, 90)
hat_servos_1.SetAngle(3, 90)
hat_servos_1.SetAngle(4, 90)
wait(1)
hat_servos_1.SetAngle(1, 180)
hat_servos_1.SetAngle(2, 180)
hat_servos_1.SetAngle(3, 180)
hat_servos_1.SetAngle(4, 180)
wait(1)
hat_servos_1.SetAngle(1, 90)
hat_servos_1.SetAngle(2, 90)
hat_servos_1.SetAngle(3, 90)
hat_servos_1.SetAngle(4, 90)
wait(1)
hat_servos_1.SetAngle(1, 0)
hat_servos_1.SetAngle(2, 0)
hat_servos_1.SetAngle(3, 0)
hat_servos_1.SetAngle(4, 0)
wait(1)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo/uiflow_block_hat_servos_angle.svg">

```python
hat_servos_0.SetAngle(1, 0)
```

- Set the rotation angle of the specified servo channel. The current angle is set to 0 degrees.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo/uiflow_block_hat_servos_write.svg">

```python
hat_servos_0.SetPulse(1, 600)
```

- Set the pulse width of the specified servo channel. The current value is 600 microseconds.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo/uiflow_block_servos_set_all.svg">

```python
hat_servos_0.SetRGB(0xff0000)
```

- Set the color of all LEDs. The current color is red.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo/uiflow_block_servos_set_all_rgb.svg">

```python
hat_servos_0.SetRGB(0x000000)
```

- Set the RGB strip color by specifying red, green, and blue values. The current color is (0,0,0), which is black (LEDs off).