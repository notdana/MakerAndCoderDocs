# Hat DAC2

> Outputs the read voltage value.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac2/uiflow_block_hat_dac2_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_dac2_0 = hat.get(hat.DAC2)

hat_dac2_0.setDACOutputVoltageRange(hat_dac2_0.RANGE_5V)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac2/uiflow_block_hat_dac2_setDACOutputVoltageRange.svg">

```python
hat_dac2_0.setDACOutputVoltageRange(hat_dac2_0.RANGE_5V)
```

- Sets the DAC output voltage range; currently set to `RANGE_5V`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac2/uiflow_block_hat_dac2_setVoltage.svg">

```python
hat_dac2_0.setVoltage(5, channel=hat_dac2_0.CHANNEL_0)
```

- Sets the output voltage for Channel 0 to 5V.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac2/uiflow_block_hat_dac2_setVoltageBoth.svg">

```python
hat_dac2_0.setVoltageBoth(5, 5)
```

- Sets the output voltage for both Channel 0 and Channel 1 to 5V each.