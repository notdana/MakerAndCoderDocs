# Atomic Motion Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.Motion import Motion
import time

motion = Motion()
motion.set_motor_speed(1, 127)
motion.set_motor_speed(2, -127)
while True:
  motion.set_servo_angle(1, 90)
  motion.set_servo_angle(2, 90)
  motion.set_servo_angle(3, 90)
  motion.set_servo_angle(4, 90)
  wait(1)
  motion.set_servo_angle(1, 180)
  motion.set_servo_angle(2, 180)
  motion.set_servo_angle(3, 180)
  motion.set_servo_angle(4, 180)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_init.svg">

```python
from base.Motion import Motion
motion = Motion()
```

- Initialize Atomic Motion.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_set_motor_speed.svg">

```python
motion.set_motor_speed(ch, speed)
```

- Control DC motor speed::
  - ch: 1-2
  - speed: -127 ~ +127, with 0 to stop.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_get_motor_speed.svg">

```python
motion.get_motor_speed(ch)
```

- Get the DC motor speed configuration:
  - ch: 1-2


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_set_servo_angle.svg">

```python
motion.set_servo_angle(ch, angle)
```

- Control the servo rotation angle
  - ch: 1-4
  - angle: 0-180

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_get_servo_angle.svg">

```python
motion.get_servo_angle(ch)
```

- Get the servo rotation angle:
  - ch: 1-4

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_set_servo_pulse.svg">

```python
motion.set_servo_pulse(ch, pulse)
```

- Control the servo pulse time (us):
  - ch: 1-4
  - pulse: 500-2500

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/motion/uiflow_block_motion_get_servo_pulse.svg">

```python
motion.get_servo_pulse(ch)
```

- Get the servo pulse time (us):
  - ch: 1-4

