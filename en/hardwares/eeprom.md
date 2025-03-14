# EEPROM

## Example

Write a variable to EEPROM and display it on the screen.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/eeprom/uiflow_block_eeprom_demo.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import nvs

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

label0 = M5Label('label0', x=137, y=88, color=0x000, font=FONT_MONT_14, parent=None)

nvs.write(str('q'), '1')
while True:
  label0.set_text(str(nvs.read_str('q')))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/eeprom/uiflow_block_eeprom_write_str.svg"> 

```python
nvs.write(str(''), '')
```

- Initialize EEPROM, set a variable, and assign a value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/eeprom/uiflow_block_eeprom_read_str.svg"> 

```python
str(nvs.read_str('q'))
```

- Read a variable from EEPROM.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/eeprom/uiflow_block_eeprom_read_int.svg"> 

```python
str(nvs.read_int('q'))
```

- Convert the variable from EEPROM to an integer and output it.