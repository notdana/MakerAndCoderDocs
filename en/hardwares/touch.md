# Touch

## Example

Display touch coordinates and touch status on the screen.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/touch/uiflow_block_touch_demo.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from m5stack import touch

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

label0 = M5Label('label0', x=123, y=59, color=0x000, font=FONT_MONT_14, parent=None)
label1 = M5Label('label1', x=121, y=93, color=0x000, font=FONT_MONT_14, parent=None)

while True:
  label0.set_text(str(touch.read()))
  label1.set_text(str(touch.status()))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/touch/uiflow_block_touch_get_touch_coordinate.svg"> 

```python
str(touch.read())
```

- Get the touch point coordinates on the screen for x and y axes (x: 0-320; y: 0-240).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/touch/uiflow_block_touch_get_touch_coordinate_x.svg"> 

```python
str(touch.read()[0])
```

- Get the x-axis coordinate of the touch point on the screen (returns 0-320).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/touch/uiflow_block_touch_get_touch_coordinate_y.svg"> 

```python
str(touch.read()[1])
```

- Get the y-axis coordinate of the touch point on the screen (returns 0-240).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/touch/uiflow_block_touch_get_touch_press_status.svg"> 

```python
str(touch.status())
```

- Returns true or false; returns true if the screen is being touched, and false if it is not.