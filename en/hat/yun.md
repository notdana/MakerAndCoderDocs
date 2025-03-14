# Hat Yun

## Example

> Sets the light color to red and retrieves sensor data for temperature, humidity, and atmospheric pressure.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_hat_yun_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_yun_0 = hat.get(hat.YUN)

hat_yun_0.SetRGBAll(0xff0000)
while True:
  print(hat_yun_0.temperature)
  print(hat_yun_0.humidity)
  print(hat_yun_0.pressure)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_get_hat_yun_brightness.svg">

```python

```

- Retrieves the brightness level of the Yun device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_get_hat_yun_humidity.svg">

```python

```

- Retrieves the humidity level from the Yun device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_get_hat_yun_pressure.svg">

```python

```

- Retrieves the atmospheric pressure from the Yun device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_get_hat_yun_temperature.svg">

```python

```

- Retrieves the temperature from the Yun device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_yun_hat_set_color.svg">

```python

```

- Sets the color of a specific LED on the Yun device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/yun/uiflow_block_yun_hat_set_color_all.svg">

```python

```

- Sets the color of all LEDs on the Yun device.