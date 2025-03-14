# Hat Roverc

## Example

> Loops to control the wheel speed and direction of RoverC, moving it in different directions with a 1-second delay.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_roverc_0 = hat.get(hat.ROVERC)

while True:
  hat_roverc_0.SetAllPulse(20, 20, 20, 20)
  wait(1)
  hat_roverc_0.SetSpeed(0, (-20), 0)
  wait(1)
  hat_roverc_0.SetAllPulse(20, (-20), (-20), 20)
  wait(1)
  hat_roverc_0.SetSpeed((-20), 0, 0)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_set_all_pulse.svg">

```python
hat_roverc_0.SetAllPulse(0, 0, 0, 0)
```

- Sets the pulse width for RoverC's four wheels: front-left, front-right, rear-left, and rear-right, controlling the movement of each wheel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_set_pulse.svg">

```python
hat_roverc_0.SetPulse(0, 0)
```

- Sets the pulse width for a specified wheel; here, the front-left wheel is specified.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_set_servo_angle.svg">

```python
hat_roverc_0.SetServoAngle(0, 0)
```

- Sets the angle position of a specified servo, with the value representing the rotation angle.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_set_servo_pulse.svg">

```python
hat_roverc_0.SetServoPulse(0, 500)
```

- Sets the pulse width for a specified servo, controlling its action.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/roverc/uiflow_block_hat_roverc_set_speed.svg">

```python
hat_roverc_0.SetSpeed(0, 0, 0)
```

- Sets the movement speed of RoverC, controlling speed across the X, Y, and Z axes.