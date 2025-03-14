# [Unit CardKB](/en/unit/cardkb)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/cardkb/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
cardkb_0 = unit.get(unit.CARDKB, unit.PORTA)

while True:
  print(cardkb_0.keyData)
  print(cardkb_0.keyString)
  wait(0.1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/cardkb/uiflow_block_cardkb_getkey.svg">

```python
print(cardkb_0.keyData)
```

- Return the ASIIC value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/cardkb/uiflow_block_cardkb_getpress.svg">

```python
print(cardkb_0.isNewKeyPress())
```

- Return character

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/cardkb/uiflow_block_cardkb_getstring.svg">

```python
print(cardkb_0.keyString)
```

- Detect the key, press it to return to true
