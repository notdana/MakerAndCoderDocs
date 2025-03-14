# [Unit DLight](/en/unit/DLight%20Unit)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dlight/uiflow_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
dlight_0 = unit.get(unit.DLIGHT, unit.PORTA)

def buttonA_wasPressed():
  # global params
  dlight_0.set_mode(0x10)
  print('Continous Mode 1')
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  dlight_0.set_mode(0x20)
  print('One Shot Mode 1')
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  # global params
  dlight_0.set_mode(0x07)
  print('Reset')
  pass
btnC.wasPressed(buttonC_wasPressed)


while True:
  print((str('lux value:') + str((dlight_0.get_lux()))))
  wait_ms(250)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dlight/uiflow_block_unit_dlight_get_lux.svg">

```python
print((str('Lux value:') + str((dlight_0.get_lux()))))
```

- Get the ambient illumination value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dlight/uiflow_block_unit_dlight_set_continous_mode.svg">

```python
dlight_0.set_mode(0x10)
```

- Continuous mode
  - H-Res1
  - H-Res2
  - L-Res

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dlight/uiflow_block_unit_dlight_set_one_shot_mode.svg">

```python
dlight_0.set_mode(0x20)
```

- Single lens mode
  - H-Res1
  - H-Res2
  - L-Res

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dlight/uiflow_block_unit_dlight_set_state_mode.svg">

```python
dlight_0.set_mode(0x00)
```

- Device status control

