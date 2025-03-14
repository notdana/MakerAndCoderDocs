# Hat DAC

> Outputs voltage and raw data.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac/uiflow_block_hat_dac_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_dac_0 = hat.get(hat.DAC)

hat_dac_0.setVoltage(1, save=True)
hat_dac_0.writeData(1, save=True)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac/uiflow_block_hat_dac_state.svg">

```python
hat_dac_0.setVoltage(1, save=True)
```

- Sets the DAC output voltage, with an option to save the current state (`save=True`).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dac/uiflow_block_hat_dac_writeData.svg">

```python
hat_dac_0.writeData(1, save=True)
```

- Sets the DAC output voltage using raw data and saves the state (`save=True`).