
# Pin Servo

## Example

Initialization pin is used for general servo control (50Hz, 500-2500us), for angle control.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/pin_servo/uiflow_block_pin_servo_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *
from servo import Servo
import time

setScreenColor(0x222222)

servo0 = Servo(26,50,500,2500,180)
while True:
  servo0.write_angle(0)
  wait(1)
  servo0.write_angle(180)
  wait(1)
  servo0.write_us(500)
  wait(1)
  servo0.write_us(2500)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/pin_servo/uiflow_block_pin_servo_init.svg"> 


```python
from servo import Servo
servo0 = Servo(26,50,500,2500,180)
```

- Servo initialization settings:
  - Pin: Pin Number
  - freq: Servo Signal Frequency
  - min: Minimum pulse width
  - max: Maximum pulse width
  - angle angle: Rudder angle range

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/pin_servo/uiflow_block_pin_servo_write_angle.svg"> 

```python
servo0.write_angle(180)
```

- Control the servo to rotate a specified angle


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/pin_servo/uiflow_block_pin_servo_write_us.svg"> 


```python
servo0.write_us(2500)
```

- Controls the high level time of the drive signal output cycle


