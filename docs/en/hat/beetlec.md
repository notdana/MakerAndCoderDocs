# Hat Beetlec

## Example

> The car rotates left and right, moves forward, and sets all lights to green.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/beetlec/uiflow_block_hat_beetlec_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_BeetleC_1 = hat.get(hat.BEETLEC)

hat_BeetleC_1.SetAllRGB(0x33ff33)
while True:
  hat_BeetleC_1.SetPulse(0, 255)
  hat_BeetleC_1.SetPulse(1, 0)
  wait(1)
  hat_BeetleC_1.SetPulse(0, 0)
  hat_BeetleC_1.SetPulse(1, 255)
  wait(1)
  hat_BeetleC_1.SetPulse(0, 255)
  hat_BeetleC_1.SetPulse(1, 255)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/beetlec/uiflow_block_beetleC_hat_set_color.svg">

```python
hat_BeetleC_0.SetRGB(0, 0xff0000)
```

- Set the RGB color at index 0 on BeetleC; currently set to red.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/beetlec/uiflow_block_beetleC_hat_set_color_all.svg">

```python
hat_BeetleC_0.SetAllRGB(0xff0000)
```

- Set all RGB colors on BeetleC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/beetlec/uiflow_block_set_beetleC_wheel_speed.svg">

```python
hat_BeetleC_0.SetPulse(0, 1)
```

- Set the speed of the wheel on BeetleC.