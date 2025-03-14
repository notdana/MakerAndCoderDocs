# Hat NCIR

## Example

> Prints sensor values to the serial monitor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/ncir/uiflow_block_hat_ncir_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_ncir_0 = hat.get(hat.NCIR)

while True:
  print(hat_ncir_0.temperature)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/ncir/uiflow_block_hat_ncir_read.svg">

```python
hat_ncir_0.temperature
```

- Reads data from the specified infrared temperature sensor module.