# Hat Thermal

## Example

> Retrieves and prints the center temperature, maximum temperature, and minimum temperature from the sensor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_thermal_0 = hat.get(hat.MLX90640)

while True:
  print(hat_thermal_0.getCenterTmp())
  print(hat_thermal_0.getMaxTmp())
  print(hat_thermal_0.getMinTmp())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_get_center_temperature.svg">

```python
hat_thermal_0.getCenterTmp()
```

- Retrieves the temperature at the center of the sensor’s field of view.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_get_max_temperature.svg">

```python
hat_thermal_0.getMaxTmp()
```

- Retrieves the highest temperature detected by the sensor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_get_min_temperature.svg">

```python
hat_thermal_0.getMinTmp()
```

- Retrieves the lowest temperature detected by the sensor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_get_temperature.svg">

```python
hat_thermal_0.getTmp(0, 0)
```

- Retrieves the temperature at a specified pixel location (0, 0 in this example).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_set_max_visible_temperature.svg">

```python
hat_thermal_0.setColorMaxTmp(35)
```

- Sets the maximum visible temperature for color mapping (e.g., setting max to 35°C).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_set_min_visible_temperature.svg">

```python
hat_thermal_0.setColorMinTmp(24)
```

- Sets the minimum visible temperature for color mapping (e.g., setting min to 24°C).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/thermal/uiflow_block_hat_thermal_update.svg">

```python
hat_thermal_0.update(x=0, y=0, show=True, showCenter=True)
```

- Updates the sensor display with optional settings for showing the center point and coordinates.