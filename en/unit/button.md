# Unit Button

## Example

Output button state

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/button/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
button_0 = unit.get(unit.BUTTON, unit.PORTB)

while True:
  if button_0.wasPressed():
    print('Pressed')
  else:
    print('Released')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/button/uiflow_block_unit_button_callback.svg">

```python
def button_0_wasPressed_cb():
  # global params
  pass
button_0.wasPressed(button_0_wasPressed_cb)

```

- Callback function (trigger button)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/button/uiflow_block_unit_button_state.svg">

```python
print((str('status:') + str((button_0.wasPressed()))))
```

- Gets the state after the button is triggered

