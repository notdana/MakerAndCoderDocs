# [Unit 8Angle](/en/unit/8Angle)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
angle8_0 = unit.get(unit.ANGLE8, unit.PORTA)

while True:
  print(angle8_0.get_button_status())
  print(angle8_0.get_adc12_raw(0))
  print(angle8_0.read_status(0xFE))
  angle8_0.set_LED_RGB24(0, 50, 50, 50, 50)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_adc_12raw.svg">

```python
print(angle8_0.get_adc12_raw(0))
```

- Gets a value of 12 as ADC from a channel (0-7)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_adc_8raw.svg">

```python
print(angle8_0.get_adc8_raw(0))
```

- Gets an 8-bit ADC value from a channel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_button_status.svg">

```python
print(angle8_0.get_button_status())
```

- ets an 8-bit ADC value from a channel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_init.svg">

```python
angle8_0.init_i2c_address(0x43)
```

- Initializes the I2C communication address of the device (default 0x43)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_read_status.svg">

```python
print(angle8_0.read_status(0xFE))
```

- Get the firmware version

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_set_i2c_address.svg">

```python
angle8_0.set_i2c_address(0x43)
```

- Set the I2C address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_set_led_rgb.svg">

```python
angle8_0.set_LED_RGB24(0, 50, 50, 50, 50)
```

- Set the RGB value and brightness for a channel (0-7)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/8angle/uiflow_block_angle8_set_led_rgb_from.svg">

```python
angle8_0.set_LED_RGB24_From(0, 8, 50, 50, 50, 50)
```

- Set RGB values and brightness for multiple channels (0-7) in batches