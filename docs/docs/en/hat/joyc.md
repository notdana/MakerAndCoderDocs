# Hat Joyc

## Example

> Sets the LED color to red and continuously prints the joystick’s X and Y potentiometer values, rotation angle, and button press state in the serial output.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_joyc_0 = hat.get(hat.JOYC)

hat_joyc_0.SetLedColor(0xff0000)
while True:
  print(hat_joyc_0.GetX(0))
  print(hat_joyc_0.GetY(0))
  print(hat_joyc_0.GetAngle(0))
  print(hat_joyc_0.GetPress(0))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_get_angle.svg">

```python
hat_joyc_0.GetAngle(0)
```

- Retrieves the angle of the joystick.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_get_distance.svg">

```python
hat_joyc_0.GetDistance(0)
```

- Gets the distance value of the joystick.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_get_press.svg">

```python
hat_joyc_0.GetPress(0)
```

- Retrieves the press state of the joystick button.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_get_x.svg">

```python
hat_joyc_0.GetX(0)
```

- Gets the joystick value on the X-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_get_y.svg">

```python
hat_joyc_0.GetY(0)
```

- Gets the joystick value on the Y-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joyc/uiflow_block_hat_joyc_set_led_color.svg">

```python
hat_joyc_0.SetLedColor(0x0)
```

- Sets the LED color (combination of red, green, and blue).