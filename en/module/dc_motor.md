# Module DC Motor

#> Control four DC motors to rotate clockwise for a while, then rotate counterclockwise, and finally stop all motors.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/dc_motor/uiflow_block_dc_motor_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x111111)

lego_motor = module.get(module.LEGO)
LegoM1 = NXT_Motor(1)
LegoM2 = NXT_Motor(2)
LegoM3 = NXT_Motor(3)
LegoM4 = NXT_Motor(4)
while True:
  lego_motor.M1.set_pwm(180)
  lego_motor.M2.set_pwm(180)
  lego_motor.M3.set_pwm(180)
  lego_motor.M4.set_pwm(180)
  wait(1)
  lego_motor.M1.set_pwm(-180)
  lego_motor.M2.set_pwm(-180)
  lego_motor.M3.set_pwm(-180)
  lego_motor.M4.set_pwm(-180)
  wait(1)
  lego_motor.M1.stop()
  lego_motor.M2.stop()
  lego_motor.M3.stop()
  lego_motor.M4.stop()
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/dc_motor/uiflow_block_lego_clear.svg">

```python
lego_motor.M1.encode_clear()
```

- Clears or resets the encoder value associated with the DC motor. Encoder values are typically used to track the motor's rotational position.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/dc_motor/uiflow_block_lego_read_encoder.svg">

```python
lego_motor.M1.encoder_read()
```

- Reads the encoder value of the DC motor. The encoder value is usually returned as an integer, representing the angle or steps the motor has rotated.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/dc_motor/uiflow_block_lego_set_pwm.svg">

```python
lego_motor.M1.set_pwm(0)
```

- Sets the rotation direction and PWM (Pulse Width Modulation) value of the DC motor. The direction can be set to clockwise or counterclockwise, and the PWM value controls the motor's speed, usually ranging from 0 to 255.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/dc_motor/uiflow_block_lego_stop.svg">

```python
lego_motor.M1.stop()
```

- Stops the rotation of the DC motor.