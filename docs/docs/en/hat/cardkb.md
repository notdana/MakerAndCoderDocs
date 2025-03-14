# Hat CardKB

## Example

> Prints the value of the pressed key.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cardkb/uiflow_block_hat_cardkb_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_cardkb_1 = hat.get(hat.CARDKB)

print(hat_cardkb_1.keyData)
print(hat_cardkb_1.keyString)
print(hat_cardkb_1.isNewKeyPress())
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cardkb/uiflow_block_hat_cardkb_get_key.svg">

```python
hat_cardkb_0.keyData
```

- Get the value of the single key pressed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cardkb/uiflow_block_hat_cardkb_get_pressed.svg">

```python
hat_cardkb_0.isNewKeyPress()
```

- Get the status of the currently pressed key.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cardkb/uiflow_block_hat_cardkb_get_string.svg">

```python
hat_cardkb_0.keyString
```

- Get the input string.