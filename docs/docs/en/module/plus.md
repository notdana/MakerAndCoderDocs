# Module Plus

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/plus/uiflow_block_plus_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

setScreenColor(0x222222)

plus = module.get(module.PLUS)

while True:
  print((str('Encoder: ') + str((plus.get_encode()))))
  print((str('Button: ') + str((plus.get_press()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/plus/uiflow_block_plus_clean_encode.svg">

```python
plus.clean_encode()
```

- Clears the current encoder value, resetting it to zero.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/plus/uiflow_block_plus_get_encode.svg">

```python
plus.get_encode()
```

- Retrieves the current encoder value. The returned value represents the current position of the encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/plus/uiflow_block_plus_get_press.svg">

```python
plus.get_press()
```

- Retrieves the press state of the button. The returned value indicates whether the button is currently pressed.