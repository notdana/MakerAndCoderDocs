# Hat 8Servo V1.1

> Control multiple servos to rotate at specific angles every second in a loop. You can continue to add more servos if needed.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_8servov1.1_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_servos_1 = hat.get(hat.SERVOS)

hat_8servos_2.set_pwr_ctrl(1)
while True:
  hat_8servos_2.write_servo_angle(1,0)
  hat_8servos_2.write_servo_angle(2,0)
  hat_8servos_2.write_servo_angle(3,0)
  hat_8servos_2.write_servo_angle(4,0)
  wait(1)
  hat_8servos_2.write_servo_angle(1,90)
  hat_8servos_2.write_servo_angle(2,90)
  hat_8servos_2.write_servo_angle(3,90)
  hat_8servos_2.write_servo_angle(4,90)
  wait(1)
  hat_8servos_2.write_servo_angle(1,180)
  hat_8servos_2.write_servo_angle(2,180)
  hat_8servos_2.write_servo_angle(3,180)
  hat_8servos_2.write_servo_angle(4,180)
  wait(1)
  hat_8servos_2.write_servo_angle(1,90)
  hat_8servos_2.write_servo_angle(2,90)
  hat_8servos_2.write_servo_angle(3,90)
  hat_8servos_2.write_servo_angle(4,90)
  wait(1)
  hat_8servos_2.write_servo_angle(1,0)
  hat_8servos_2.write_servo_angle(2,0)
  hat_8servos_2.write_servo_angle(3,0)
  hat_8servos_2.write_servo_angle(4,0)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_get_power_control.svg">
 
```python
hat_8servos_1.get_pwr_ctrl()
```

- Get the power control status of the servos.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_read_servo_angle.svg">

```python
hat_8servos_1.read_servo_angle(1)
```

- Read the angle of the specified servo channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_read_servo_pulse.svg">

```python
hat_8servos_1.read_servo_pulse(1)
```

- Read the pulse width of the specified servo channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_set_power_control.svg">

```python
hat_8servos_1.set_pwr_ctrl(1)
```

- Set the power control for the servos.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_write_servo_angle.svg">

```python
hat_8servos_1.write_servo_angle(1,0)
```

- Set the angle of the specified servo channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/8servo_v1.1/uiflow_block_hat_8servo_write_servo_pulse.svg">

```python
hat_8servos_1.write_servo_pulse(1,500)
```

- Set the pulse width of the specified servo channel.