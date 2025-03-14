# DAC

##  Example

Output waveforms at pin 25 using the dac0 channel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *
import machine
import time

setScreenColor(0x222222)

dac0 = machine.DAC(26)
while True:
  dac0.write(0)
  wait(1)
  dac0.write(255)
  wait(1)
  wait_ms(2)

```


#### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_init.svg"> 

```python
dac0 = machine.DAC([pin])
```

- Setting the conversion channel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_write_value.svg"> 

```python
dac0.write(255)
```

- Write DAC conversion value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_write_beep.svg"> 

```python
dac0.beep(1800, 200, 0)
```

- Configure the outputs to drive the buzzer frequency, time and amplitude.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_write_waveform.svg"> 

```python
dac0.waveform(1800, dac0.SINE, duration=200, scale=0, offset=0, invert=0)
```

- Setting the output waveform frequency amplitude offset

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_write_waveform_stop.svg"> 

```python
dac0.stopwave()
```

- Stop Output

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/dac/uiflow_block_dac_set_freq.svg"> 

```python
dac0.freq(1800)
```

- Setting the output frequency

