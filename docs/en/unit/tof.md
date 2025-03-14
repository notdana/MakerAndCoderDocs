# [Unit ToF](/en/unit/TOF)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
tof_0 = unit.get(unit.TOF, unit.PORTA)

while True:
  print(tof_0.distance)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof/uiflow_block_unit_tof_state.svg">

```python
print(tof_0.distance)
```

- Gets the distance measured by the Unit ToF