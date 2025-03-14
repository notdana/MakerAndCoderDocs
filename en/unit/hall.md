# [Unit Hall](/en/unit/hall)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hall/uiflow_block_ecample.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
hall_0 = unit.get(unit.HALL, unit.PORTA)

while True:
  print((str('hall:') + str((hall_0.value()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hall/uiflow_block_hall_value.svg">

```python
print(hall_0.value())
```

- Obtain the current status of the Hall sensor

