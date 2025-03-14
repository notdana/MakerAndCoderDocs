# [Unit Joystick](/en/unit/joystick)

## Example

Gets the current state of the joystick

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
joystick_0 = unit.get(unit.JOYSTICK, unit.PORTA)

while True:
  print(joystick_0.X)
  print(joystick_0.Y)
  print(joystick_0.Press)
  wait(0.2)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_joystick_press.svg">

```python
print(joystick_0.Press)
```

- Get is pressed Returns the key value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_joystick_reversal_x.svg">

```python
print(joystick_0.InvertX)
```

- Get Reverse X Returns the reverse X-axis data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_joystick_reversal_y.svg">

```python
print(joystick_0.InvertY)
```

- Get Reverse Y Returns the reverse data of the Y-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_joystick_x.svg">

```python
print(joystick_0.X)
```

- Get X Returns the X-axis data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick/uiflow_block_joystick_y.svg">

```python
print(joystick_0.Y)
```

- Get Y Returns the data of the Y-axis

