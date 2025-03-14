# [Unit FlashLight](/en/unit/FlashLight)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/flash_light/uiflow_block_example.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import unit

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
flash_0 = unit.get(unit.FLASH_LIGHT, unit.PORTB)

flash_0.flash_ctrl(7, False, 2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/flash_light/uiflow_block_unit_flashlight_control.svg">

```python
flash_0.flash_ctrl(0, False, 2)
```

- Set flash control (set duty ratio 30%-100%, and FlashLight)

