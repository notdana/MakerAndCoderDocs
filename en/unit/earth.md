# Unit Earth

## Example Program

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/earth/uiflow_block_earth_demo.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import unit

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
earth_0 = unit.get(unit.EARTH, unit.PORTB)

while True:
  print((str('Analog Value:') + str((earth_0.analogValue))))
  print((str('Digital Value:') + str((earth_0.digitalValue))))
  wait_ms(2)
```

## Function Description

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/earth/uiflow_block_earth_a_read.svg">

```python
earth_0.analogValue
```

- Gets the analog value from the specified Earth device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/earth/uiflow_block_earth_d_read.svg">

```python
earth_0.digitalValue
```

- Gets the digital value from the specified Earth device.