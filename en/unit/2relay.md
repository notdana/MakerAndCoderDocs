# [Unit 2Relay](/en/unit/2relay)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/2relay/uiflow_block_unit_relay2_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
relay2_0 = unit.get(unit.RELAY2, unit.PORTA)

while True:
  relay2_0.set_value(3, 1)
  wait(1)
  relay2_0.set_value(3, 0)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/2relay/uiflow_block_unit_relay2_control.svg">

```python
relay2_0.set_value(ch, status)
```

- Relay control:
  - ch:
    - 1:control relay 1
    - 2:control relay 2
    - 3:control all relay
  - status:
    - 1:on
    - 0:off


