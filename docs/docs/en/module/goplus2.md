# Module13.2 GoPlus2

## Example

#> Toggle the angle values of 4 servos every second, and change the speed and direction of rotation of the motors.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x222222)

go_plus_2 = module.get(module.GOPLUS2)

label1 = M5TextBox(0, 81, "btnA: Set up Servo and MA", lcd.FONT_UNICODE, 0x19fe46, rotate=0)
label2 = M5TextBox(0, 123, "btnB: Set up Servo and MB", lcd.FONT_UNICODE, 0xfe6019, rotate=0)
title0 = M5Title(title="GoPlus 2", x=125, fgcolor=0xFFFFFF, bgcolor=0x0000FF)

def buttonA_wasPressed():
  # global params
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  pass
btnB.wasPressed(buttonB_wasPressed)

while True:
  go_plus_2.set_servo_angle(go_plus_2.S1, 180)
  go_plus_2.set_servo_angle(go_plus_2.S2, 0)
  go_plus_2.set_servo_angle(go_plus_2.S3, 90)
  go_plus_2.set_servo_angle(go_plus_2.S4, 45)
  go_plus_2.set_motor_speed(go_plus_2.MB, 0)
  go_plus_2.set_motor_speed(go_plus_2.MA, 127)
  wait(1)
  go_plus_2.set_servo_plus(go_plus_2.S1, 800)
  go_plus_2.set_servo_plus(go_plus_2.S2, 1500)
  go_plus_2.set_servo_plus(go_plus_2.S3, 500)
  go_plus_2.set_servo_plus(go_plus_2.S4, 2500)
  go_plus_2.set_motor_speed(go_plus_2.MA, 0)
  go_plus_2.set_motor_speed(go_plus_2.MB, (-127))
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_analog_read.svg">

```python
go_plus_2.analog_read(go_plus_2.PB1)
```

- Read the analog value of the pin. Returns an analog value representing the voltage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_digital_read.svg">

```python
go_plus_2.digital_read(go_plus_2.PB1)
```

- Read the digital value of the pin. Returns a digital value representing the high or low state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_digital_write.svg">

```python
go_plus_2.digital_write(go_plus_2.PB1, 0)
```

- Set the pin to digital output 0 (low level).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_set_motor_speed.svg">

```python
 go_plus_2.set_motor_speed(go_plus_2.MA, 0)
```

- Set the motor speed. The speed value can be positive or negative, used to control the motor's speed and direction.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_set_servo_angle.svg">

```python
go_plus_2.set_servo_angle(go_plus_2.S1, 0)
```

- Set the angle of servo S1 to 0. The angle value can be within the servo's range and is used to control the servo's position.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/goplus2/uiflow_block_go_plus2_set_servo_plus.svg">

```python
 go_plus_2.set_servo_plus(go_plus_2.S1, 500)
```

- Adjust the position of the servo by increasing the specified increment value (PWM).