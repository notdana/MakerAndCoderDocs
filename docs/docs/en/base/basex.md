#  Base X

#> Set the speed of motor M1 in normal mode, set the target position in position mode, set the target speed in speed mode, and print the motor's encoder value in real-time in each mode.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x222222)

mode = None

base_x = module.get(module.BASE_X)

while True:
  print((str('') + str((base_x.get_encoder(1)))))
  base_x.set_mode(1, base_x.NORMAL_MODE)
  base_x.set_motor_speed(1, 100)
  wait(1)
  print((str('') + str((base_x.get_encoder(1)))))
  base_x.set_mode(1, base_x.POSITION_MODE)
  base_x.set_position_pid_max_speed(1, 50)
  base_x.set_position_point(1, 1000)
  wait(1)
  print((str('') + str((base_x.get_encoder(1)))))
  base_x.set_mode(1, base_x.SPEED_MODE)
  base_x.set_speed_point(1, 100)
  wait(1)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_get_encoder.svg">

```python
base_x.get_encoder(1)
```

- Retrieves the encoder value of the motor, returning the current reading of the encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_get_speed_20ms.svg">

```python
base_x.get_speed_20ms(1)
```

- Retrieves the motor speed over a 20ms interval, returning the speed of the motor during this time period.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_run_ahead.svg">

```python
base_x.run_ahead(1, 0)
```

- Sets the motor to run ahead by a specified distance or angle. The parameter value is an integer, indicating the number of steps or distance the motor will run ahead.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_encoder.svg">

```python
base_x.set_encoder(1, 0)
```

- Sets the motor's encoder value to the specified integer value, typically used to reset the current encoder value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_mode.svg">

```python
base_x.set_mode(1, base_x.NORMAL_MODE)
```

- Sets the motor to normal mode, operating the motor in its regular running mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_motor_speed.svg">

```python
base_x.set_motor_speed(1, 0)
```

- Sets the motor's speed. The input value of 0 sets the motor speed to 0, effectively stopping the motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_position_pid_max_speed.svg">

```python
base_x.set_position_pid_max_speed(1, 0)
```

- Sets the maximum speed for the motor in position PID control. The input value of 0 limits the maximum speed to 0 in position control.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_position_point.svg">

```python
base_x.set_position_point(1, 0)
```

- Sets the position point of the motor. The input value of 0 sets the target position of the motor to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_servo_angle.svg">

```python
base_x.set_servo_angle(1, 0)
```

- Sets the servo angle. The input value of 0 sets the servo angle to 0 degrees.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_servo_pulse.svg">

```python
base_x.set_servo_pulse(1, 0)
```

- Sets the pulse width of the servo. The input value of 0 sets the pulse width to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/basex/uiflow_block_basex_set_speed_point.svg">

```python
base_x.set_speed_point(1, 0)
```

- Sets the motor's target speed point. The input value of 0 sets the target speed to 0, meaning the motor will not run or will stop running.