# Hat DLight

## Example

> Outputs the light intensity value via serial.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dlight/uiflow_block_hat_dlight_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_dlight_0 = hat.get(hat.DLIGHT)

hat_dlight_0.set_mode(0x10)
while True:
  print(hat_dlight_0.get_lux())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dlight/uiflow_block_hat_dlight_get_lux.svg">

```python
hat_dlight_0.get_lux()
```

- Reads the light intensity value in lux.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dlight/uiflow_block_hat_dlight_set_continous_mode.svg">

```python
hat_dlight_0.set_mode(0x10)
```

- Sets continuous mode with the current selection as H-Res1, allowing continuous light intensity readings.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dlight/uiflow_block_hat_dlight_set_one_shot_mode.svg">

```python
hat_dlight_0.set_mode(0x20)
```

- Sets one-shot mode with the current selection as H-Res1, for a single light intensity reading.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/dlight/uiflow_block_hat_dlight_set_state_mode.svg">

```python
hat_dlight_0.set_mode(0x00)
```

- Controls module state, currently set to Power Down, used to turn off the device or enter low power mode.