# Hat ToF

## Example

> Retrieves and prints the distance value from the sensor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/tof/uiflow_block_hat_tof_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_tof_0 = hat.get(hat.TOF)

while True:
  print(hat_tof_0.GetDistance())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/tof/uiflow_block_hat_tof_get_distance.svg">

```python
hat_tof_0.GetDistance()
```

- Retrieves the distance data measured by the sensor.