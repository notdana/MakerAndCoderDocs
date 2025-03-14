# Hat Joystick

## Example

> Continuously prints the joystick's X and Y axis values and button press state in the serial output.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_Joystick_0 = hat.get(hat.JOYSTICK)

while True:
  print(hat_Joystick_0.X)
  print(hat_Joystick_0.Y)
  print(hat_Joystick_0.Press)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_press.svg">

```python
hat_Joystick_0.Press
```

- Checks if the joystick button is pressed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_reversal_x.svg">

```python
hat_Joystick_0.InvertX
```

- Gets the inverted value of the joystick on the X-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_reversal_y.svg">

```python
hat_Joystick_0.InvertY
```

- Gets the inverted value of the joystick on the Y-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_x.svg">

```python
hat_Joystick_0.X
```

- Gets the position value of the joystick on the X-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_y.svg">

```python
hat_Joystick_0.Y
```

- Gets the position value of the joystick on the Y-axis.