# [Unit Dual Button](/en/unit/dual_button)

## Example

Output button state

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dual_button/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
dual_button_0 = unit.get(unit.DUAL_BUTTON, unit.PORTB)

while True:
  if dual_button_0.btnBlue.wasPressed():
    rgb.setColorAll(0x000099)
    print('Blue button pressed')
  elif dual_button_0.btnRed.wasPressed():
    rgb.setColorAll(0xcc0000)
    print('Red button pressed')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dual_button/uiflow_block_unit_dual_button_callback.svg">

```python
def btnRed0_wasPressed():
  # global params
  pass
dual_button_0.btnRed.wasPressed(btnRed0_wasPressed)
```

- Callback function (trigger button)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dual_button/uiflow_block_unit_dual_button_state.svg">

```python
print((str('status:') + str((dual_button_0.btnRed.wasPressed()))))
```

- Gets the state after the button is triggered
