# Hat ADC

## Example

> Print the acquired voltage value and raw data to the serial monitor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/adc/uiflow_block_hat_adc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat
import hat

setScreenColor(0x111111)

hat_adc_1 = hat.get(hat.ADC)

print(hat_adc_1.voltage)
print(hat_adc_1.rawData())
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/adc/uiflow_block_hat_adc_raw_value.svg">

```python
hat_adc_0.rawData()
```

- Read the raw data from the ADC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/adc/uiflow_block_hat_adc_state.svg">

```python
hat_adc_0.voltage
```

- Read the voltage value from the ADC.