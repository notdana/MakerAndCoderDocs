# [Unit DAC2](/en/unit/Unit-DAC2)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac2/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
dac2_0 = unit.get(unit.DAC2, unit.PORTA)

i = None

while True:
  for i in range(4):
    dac2_0.setVoltage(i, channel=dac2_0.CHANNEL_0)
    print((str(str(i)) + str('V')))
    wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac2/uiflow_block_unit_dac2_setDACOutputVoltageRange.svg">

```python
dac2_0.setDACOutputVoltageRange(dac2_0.RANGE_5V)
```

- Set the voltage of the DAC
  - Range (5V)
  - Range (10V)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac2/uiflow_block_unit_dac2_setVoltage.svg">

```python
dac2_0.setVoltage(5, channel=dac2_0.CHANNEL_0)
```

- Sets the output voltage for a specified channel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dac2/uiflow_block_unit_dac2_setVoltageBoth.svg">

```python
dac2_0.setVoltageBoth(5, 5)
```

- Set the output voltage for channels 0 and 1

