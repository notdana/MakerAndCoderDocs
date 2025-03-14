# Hat Mini JoyC

## Example

> Sets the communication address and retrieves the X and Y axis raw potentiometer values along with the initial button status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_mini_joyc_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_mini_joyc_0 = hat.get(hat.MINI_JOYC)

hat_mini_joyc_0.init_i2c_address(0x54)
while True:
  print(hat_mini_joyc_0.get_adc12_raw(0))
  print(hat_mini_joyc_0.get_adc12_raw(1))
  print(hat_mini_joyc_0.get_button_status())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_init.svg">

```python
hat_mini_joyc_0.init_i2c_address(0x54)
```

- Initializes the I2C address for the Mini JoyC, here set to `0x54`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_10bit_value.svg">

```python
hat_mini_joyc_0.get_10bit_value()
```

- Retrieves the 10-bit resolution value from the Mini JoyC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_8bit_value.svg">

```python
hat_mini_joyc_0.get_8bit_value()
```

- Retrieves the 8-bit resolution value from the Mini JoyC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_button_status.svg">

```python
hat_mini_joyc_0.get_button_status()
```

- Retrieves the current status of the button on the Mini JoyC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_device_status.svg">

```python
hat_mini_joyc_0.get_device_status()
```

- Checks the current status of the Mini JoyC device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_offset_value.svg">

```python
hat_mini_joyc_0.get_offset_value()
```

- Retrieves the offset value for the Mini JoyC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_get_raw_value.svg">

```python
hat_mini_joyc_0.get_raw_value()
```

- Retrieves the raw ADC value from the Mini JoyC.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_set_i2c_address.svg">

```python
hat_mini_joyc_0.set_i2c_address(new_address)
```

- Changes the I2C address of the Mini JoyC to `new_address`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_set_led_rgb.svg">

```python
hat_mini_joyc_0.set_led_rgb(red, green, blue)
```

- Sets the RGB LED color on the Mini JoyC by specifying red, green, and blue values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_joyc/uiflow_block_hat_minijoyc_set_offset_value.svg">

```python
hat_mini_joyc_0.set_offset_value(offset)
```

- Sets an offset value for the Mini JoyC.