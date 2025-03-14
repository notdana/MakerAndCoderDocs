# Screen

## Example

Adjusts the screen brightness and switches the screen color.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *
import time

setScreenColor(0x222222)
lcd.setBrightness(30)

while True:
  setScreenColor(0xff0000)
  wait(1)
  setScreenColor(0x3366ff)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_set_backgroundcolor.svg"> 

```python
setScreenColor(0xff0000)
```

- Setting the screen color
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_set_backgroundcolor_rgb_value.svg"> 

```python
setScreenColor(0xff0000)
```
 
- Set the screen color, and modify the color by modifying the RGB value.
  - (R:0-255  G:0-255 B:0-255)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_set_backgroundcolor_option.svg"> 

```python
setScreenColor(0xff0000)
```

- Setting the color data type
  - `Palette`: switch screen colors by directly selecting the color panel
  - `RGB`: Enter RGB values to toggle the color panel colors.
  - `HEX`: input color converted to hexadecimal value to switch values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_set_rotate_mode.svg"> 

```python
lcd.setRotation(0)
```

- rotate the screen
  - "0": 270° counterclockwise rotation
  - "1": 180° counterclockwise rotation
  - "2": 90° counterclockwise rotation
  - "3": 0° rotation, horizontal display

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/ui/screen/uiflow_block_screen_set_brightness.svg"> 

```python
lcd.setBrightness(30)
```

- Set the screen brightness, the value range is 0-255, integer type, the bigger the value, the bigger the brightness.
