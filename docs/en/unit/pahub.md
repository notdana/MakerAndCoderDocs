# Unit Pahub

## Example

Through the Unit PaHUB branch line, connect multiple Unit ToF to realize the laser ranging function of Unit ToF

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
tof_0 = unit.get(unit.TOF, unit.PAHUB0)

label0 = M5TextBox(130, 119, "label0", lcd.FONT_Default, 0xFFFFFF, rotate=0)
pahub_0.select(0, 1)
while True:
  print(tof_0.distance)
  label0.setText(str(tof_0.distance))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_pahub_only_on.svg">

```python
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
```

- Set the channel status to Open (Channel selection)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_pahub_only_on_input.svg">

```python
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
```

- Set channel status to open (channel controlled by variable)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_pahub_port.svg">

```python
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
```

- Set the value (hexadecimal) corresponding to the channel for communication

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_pahub_select.svg">

```python
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
```

- Set channel status (Channel selection)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pahub/uiflow_block_pahub_select_input.svg">

```python
pahub_0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
```

- et channel state by variable (channel variable control)
