# Hat Balac

## Example

> Control the balac to move forward, turn left or right, and move backward.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/balac/uiflow_block_balac_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

balac = hat.get(hat.BALAC)

balac.set_motor_speed(1, 50)
balac.set_motor_speed(2, 50)
wait(1)
balac.set_motor_speed(1, 50)
balac.set_motor_speed(2, 0)
wait(1)
balac.set_motor_speed(1, 0)
balac.set_motor_speed(2, 50)
wait(1)
balac.set_motor_speed(1, -50)
balac.set_motor_speed(2, -50)
wait(1)
balac.stop_motor(1)
wait(1)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/balac/uiflow_block_hat_balac_set_motor_speed.svg">

```python
balac.set_motor_speed(1, 50)
```

- Set the speed of DC Motor A, with the current speed set to 50 (maximum speed is 255).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/balac/uiflow_block_hat_balac_stop_motor.svg">

```python
balac.stop_motor(1)
```

- Stop the operation of DC Motor A.