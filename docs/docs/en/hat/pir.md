# Hat PIR

## Example

> Outputs the sensor value of the PIR motion sensor to the serial monitor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/pir/uiflow_block_hat_pir_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_pir_0 = hat.get(hat.PIR)

while True:
  print(hat_pir_0.state)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/pir/uiflow_block_hat_pir_read.svg">

```python
hat_pir_0.state
```

- Retrieves the state of the specified PIR sensor, typically used to detect motion presence.