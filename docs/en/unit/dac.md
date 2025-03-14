# [Unit DAC](/en/unit/dac)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
dac_0 = unit.get(unit.DAC, unit.PORTA)

i = None

while True:
  for i in range(4):
    dac_0.setVoltage(i,save=True)
    print((str(str(i)) + str('V')))
    wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac/uiflow_block_unit_dac_state.svg">

```python
dac_0.setVoltage(1,save=True)
```

- Set the voltage of the DAC

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac/uiflow_block_unit_dac_writeData.svg">

```python
dac_0.writeData(1,save=True)
```

- Set the DAC value

