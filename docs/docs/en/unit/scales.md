# [Unit Scales](/en/unit/scales)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
scales_0 = unit.get(unit.SCALES, unit.PORTA)

scales_0.write_rgb_led(25, 72, 26)
scales_0.write_button_offset(1)
while True:
  print((str('weight:') + str(((scales_0.read_weight(0x14)/100) - -58344))))
  print((str('button:') + str((scales_0.read_button_status(0x20)))))
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_init_i2c.svg">

```python
scales_0.init_i2c_address(0x26)
```

- Initializes the I2C address of the Unit Scales

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_get_button.svg">

```python
print(scales_0.read_button_status(0x20))
```

- Get button status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_get_led.svg">

```python
print(scales_0.read_rgb_led(False))
```

- Obtain LED status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_get_scale.svg">

```python
print(scales_0.read_weight(0x10))
```

- Get the ADC original value status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_get_status.svg">

```python
print(scales_0.read_status(0xFE))
```

- Obtain the version number

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_adc.svg">

```python
scales_0.write_offset(5000)
```

- Set the offset ADC value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_adc_offset.svg">

```python
scales_0.write_soft_offset()
```

- Set the offset current ADC value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_button_offset.svg">

```python
scales_0.write_button_offset(1)
```

- Set button deviation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_calibration.svg">

```python
scales_0.write_calibration_load(200)
```

- Set the load calibration

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_i2c.svg">

```python
scales_0.write_i2c_address(0x26)
```

- Resets the I2C address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_rgb.svg">

```python
scales_0.write_rgb_led(0, 0, 0)
```

- Set RGB color

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_rgb_sync.svg">

```python
scales_0.write_rgb_sync(0)
```

- Set the RGB LED synchronization status
  - ENABLE
  - DISABLE 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/scales/uiflow_block_unit_scales_set_zero.svg">

```python
scales_0.write_calibration_zero()
```

- Set the calibrator to zero grams

