# Hat ENV

> Outputs temperature, humidity, and atmospheric pressure values.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/env/uiflow_block_hat_env_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_env_0 = hat.get(hat.ENV)

while True:
  print(hat_env_0.pressure)
  print(hat_env_0.temperature)
  print(hat_env_0.humidity)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/env/uiflow_block_hat_env_get_humidity.svg">

```python
hat_env_0.humidity
```

- Retrieves the ambient humidity as a floating-point percentage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/env/uiflow_block_hat_env_get_temperature.svg">

```python
hat_env_0.temperature
```

- Retrieves the ambient temperature as a floating-point value in degrees Celsius.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/env/uiflow_block_hat_env_pressure.svg">

```python
hat_env_0.pressure
```

- Retrieves the ambient pressure as a floating-point value in hPa (hectopascals).