# [Mini Unit Scales](/en/unit/Unit-Mini%20Scales)

## 软件开发

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
miniscales_0 = unit.get(unit.MINISCALE, unit.PORTA)

miniscales_0.setLed(255, 0, 0)
while True:
  print((str('weight:') + str(((str((miniscales_0.weight)) + str('g'))))))
  print((str('button status:') + str((miniscales_0.button))))
  wait(1)
  wait_ms(2)
```

## 功能说明

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_calibration.svg">

```python
miniscales_0.calibration(0, adc0, 100, adc1)
```

- Calibration measuring weight

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_adc.svg">

```python
print(miniscales_0.adc)
```

- Get the ADC raw value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_average_filter.svg">

```python
print(miniscales_0.getAverageFilterLevel())
```

- Get the average filter level

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_button.svg">

```python
print(miniscales_0.button)
```

- Gets the current button status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_ema_filter.svg">

```python
print(miniscales_0.getEMAFilterAlpha())
```

- Obtain EMA filter alpha value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_lowpass_filter.svg">

```python
print(miniscales_0.getLowPassFilter())
```

- Obtain low overrate filter status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_get_weight.svg">

```python
print(miniscales_0.weight)
```

- Gets the current weight (in g, returns Float)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_reset.svg">

```python
miniscales_0.reset()
```

- Reset information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_set_average_filter.svg">

```python
miniscales_0.setAverageFilterLevel(0)
```

- Set the level of the average filter

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_set_ema_filter.svg">

```python
miniscales_0.setEMAFilterAlpha(0)
```

- Set EMA filter alpha

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_set_led.svg">

```python
miniscales_0.setLed(255, 0, 0)
```

- Set the RGB light color value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_scales/uiflow_block_unit_miniscale_set_lowpass_filter.svg">

```python
miniscales_0.setLowPassFilter(True)
```

- Set the status of the low pass rate filter

