# Module13.2 GoPlus

## Example

#> Print the analog value and voltage of the pin, then set the DC motor to run at maximum speed every second, and the servo to switch back and forth between 0° and 180°.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus/uiflow_block_go_plus_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x222222)

go_plus = module.get(module.GOPLUS)

go_plus.set_motor_speed(1, 0)
while True:
  print(go_plus.digital_read(go_plus.PB1, 0))
  print(go_plus.analog_read(go_plus.PB1))
  go_plus.set_motor_speed(1, 0)
  go_plus.set_servo(0, 0)
  wait(1)
  go_plus.set_motor_speed(1, 127)
  go_plus.set_servo(0, 180)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus/uiflow_block_go_plus_analog_read.svg">

```python
go_plus.analog_read(go_plus.PB1)
```

- Read the analog value of the pin. Returns an analog value representing the voltage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus/uiflow_block_go_plus_digital_read.svg">

```python
go_plus.digital_read(go_plus.PB1, 0)
```

- Read the digital value of the pin. Returns a digital value representing the high or low state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus/uiflow_block_go_plus_set_motor_speed.svg">

```python
 go_plus.set_motor_speed(1, 0)
```

- Set the motor speed. The speed value can be positive or negative, used to control the motor's speed and direction.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus/uiflow_block_go_plus_set_servo.svg">

```python
go_plus.set_servo(0, 0)
```

- Set the angle of the servo. The angle value can be within the servo's range and is used to control the servo's position.