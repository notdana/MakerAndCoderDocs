# Easy I/O

## Example

The numerical values of the digital and analog pins are read and displayed on the screen

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_demo1.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from easyIO import *

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

label0 = M5Label('label0', x=130, y=60, color=0x000, font=FONT_MONT_14, parent=None)
label1 = M5Label('label1', x=130, y=102, color=0x000, font=FONT_MONT_14, parent=None)

label0.set_text(str(analogRead(39)))
label1.set_text(str(digitalRead(0)))
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_analog_read_pin.svg"> 

```python
str(analogRead(39))
```

- Set the ADC pin and read the analog value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_set_analog_read_pin.svg"> 

```python
str(analogRead(39))
```

- Set the ADC pin and read the analog value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_digital_read_pin.svg"> 

```python
str(digitalRead(0))
```

- Set the digital pin and read the level value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_map.svg"> 

```python
str(map_value(0, 0, 1023, 0, 4))
```

- Map function
  - "0": The variable to be mapped
  - "0": The minimum value of the variable
  - "1023": The maximum value of the variable
  - "0": The minimum output value of the map
  - "4": The maximum output value of the map

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_analog_write_pin_duty.svg"> 

```python
analogWrite(26, 0)
```

- Set the duty cycle of the analog output pin.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_digital_write_pin_vale.svg"> 

```python
digitalWrite(26, 0)
```

- Set the output level of the digital pin.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/easyio/uiflow_block_easyio_toggle_pin.svg"> 

```python
toggleIO(26)
```

- Toggle the pin level.