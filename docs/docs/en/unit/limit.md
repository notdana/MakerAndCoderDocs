# [Unit Limit](/en/unit/limit)

## Example

Output button state

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/limit/uiflow_block_examle.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
limit_0 = unit.get(unit.LIMIT, unit.PORTB)

while True:
  if limit_0.get_switch_status():
    print((str('Button:') + str((limit_0.get_switch_status()))))
  else:
    print((str('Button:') + str((limit_0.get_switch_status()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/limit/uiflow_block_unit_limit_get_switch_status.svg">

```python
print((str('status:') + str((limit_0.get_switch_status()))))
```

- Gets the current button status

