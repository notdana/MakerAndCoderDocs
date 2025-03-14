# Hat BugC

## Example

> The car alternates between moving forward and backward, with the lights changing colors.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_bugc_0 = hat.get(hat.BUGC)

while True:
  hat_bugc_0.SetAllRGB(0xff0000)
  hat_bugc_0.SetPulse(0, 255)
  hat_bugc_0.SetPulse(1, -255)
  hat_bugc_0.SetPulse(2, 255)
  hat_bugc_0.SetPulse(3, -255)
  wait(5)
  hat_bugc_0.SetAllRGB(0x00ff00)
  hat_bugc_0.SetAllPulse(-255, 255, -255, 255)
  wait(5)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_rgb_set_all.svg">

```python
hat.get(hat.BUGC)
```

- Set the color of the RGB light strip.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_rgb_set_all2.svg">

```python
hat_bugc_0.SetRGB(0, 0xff0000)
```

- Set the color of the RGB light strip using RGB color values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_rgb_set_all_rgb.svg">

```python
hat_bugc_0.SetRGB(0, 0x000000)
```

- Set the RGB light strip color by specifying values for R (red), G (green), and B (blue).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_set_all_pulse.svg">

```python
hat_bugc_0.SetAllRGB(0x000000)
```

- Set the pulse width for all channels.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc/uiflow_block_hat_bugc_set_pulse.svg">

```python
hat_bugc_0.SetAllPulse(0, 0, 0, 0)
```

- Set the pulse width for specific channels.