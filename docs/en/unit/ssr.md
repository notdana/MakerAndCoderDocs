# [Unit SSR](/en/unit/ssr)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ssr/uiflow_block_ssr.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
ssr_0 = unit.get(unit.SSR, unit.PORTA)

while True:
  ssr_0.ssr_control(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ssr/uiflow_block_unit_ssr_control.svg">

```python
ssr_0.ssr_control(1)
```

- Turn on or off the relay
  - ON
  - OFF

