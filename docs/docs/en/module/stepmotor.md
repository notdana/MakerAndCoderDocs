# Module Stepmotor

## Example

#> Move the stepper motor back and forth at a set speed in the X, Y, and Z directions, waiting for 2 seconds after each move.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_stepmotor_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x111111)

label0 = M5TextBox(-7, -11, "STEPMOTOR Example", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)

stepmotor1 = module.get(module.STEP_MOTOR, 0x70)
stepmotor1.set_mode("distance")
while True:
  stepmotor1.turn(x=(-10),  y=(-10), z=(-10), speed=300)
  wait(2)
  stepmotor1.turn(x=10,  y=10, z=10, speed=300)
  wait(2)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_g_code.svg">

```python
stepmotor1.g_code('')
```

- Sends a G-code command to the stepper motor controller. This is typically used to control the stepper motor to execute complex paths or operations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_instance.svg">

```python
module.get(module.STEP_MOTOR, 0x70)
```

- Initializes the stepper motor and sets its I2C address to 0x70. This is the address used for communication between the stepper motor and the controller.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_lock.svg">

```python
stepmotor1.lock_motor()
```

- Locks the stepper motor, preventing it from moving when not unlocked. This is typically used to ensure the motor is in a stable state before executing operations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_move_xyz.svg">

```python
stepmotor1.turn(x=0,  y=0, z=0, speed=0)
```

- Controls the stepper motor to move in the X, Y, and Z directions, with speed determined by the Speed parameter. This block allows precise control of the stepper motor's movement.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_set_mode.svg">

```python
stepmotor1.set_mode("distance")
```

- Sets the stepper motor mode to "distance" mode. This means the motor's movement will be based on the specified distance rather than other modes (such as speed mode).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor/uiflow_block_motor_unlock.svg">

```python
stepmotor1.unlock_motor()
```

- Unlocks the stepper motor, allowing it to move freely. This block is typically used to unlock the motor after the operation is completed.