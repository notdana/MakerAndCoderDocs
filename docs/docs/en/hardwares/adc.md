# ADC

##  Example

Use adc0 channel to sample at pin 36 and read the value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/adc/uiflow_block_adc_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *
import machine

setScreenColor(0x222222)

adc0 = machine.ADC(36)
adc0.width(machine.ADC.WIDTH_12BIT)
adc0.atten(machine.ADC.ATTN_11DB)
while True:
  print(adc0.read())
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/adc/uiflow_block_adc_init.svg"> 

```python
adc0 = machine.ADC([pin])
```

- Setting the Sample Channel Pins

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/adc/uiflow_block_adc_set_width.svg"> 

```python
adc0.width(machine.ADC.WIDTH_12BIT)
```

- Setting the sample width

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/adc/uiflow_block_adc_set_atten.svg"> 

```python
adc0.atten(machine.ADC.ATTN_11DB)
```

- Setting ADC input attenuation
  - `ADC.ATTN_0DB`: 0dB attenuation, providing a maximum input voltage of 1.00v.
  - `ADC.ATTN_2_5DB`: 2.5dB attenuation, providing a maximum input voltage of approximately 1.34v.
  - `ADC.ATTN_6DB`: 6dB attenuation, providing a maximum input voltage of approximately 2.00v.
  - `ADC.ATTN_11DB`: 11dB attenuation, providing a maximum input voltage of approximately 3.6v.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/adc/uiflow_block_adc_set_read_value.svg"> 

```python
adc0.read()
```

- Read ADC value

