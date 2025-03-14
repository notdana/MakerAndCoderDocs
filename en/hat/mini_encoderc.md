# Hat Mini EncoderC

## Example

> Sets the Mini Encoder communication address and LED color to white. The encoder value and button status are continuously printed in the serial output.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/joystick/uiflow_block_hat_joystick_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_mini_encoderc_0 = hat.get(hat.MINI_ENCODERC)

hat_mini_encoderc_0.init_i2c_address(0x42)
hat_mini_encoderc_0.set_LED_RGB24(50, 50, 50)
while True:
  print(hat_mini_encoderc_0.get_counter_value())
  print(hat_mini_encoderc_0.get_button_status())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_init.svg">

```python
hat_mini_encoderc_0.init_i2c_address(0x42)
```

- Initializes the I2C address for the Mini Encoder, here set to `0x42`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_get_button_status.svg">

```python
hat_mini_encoderc_0.get_button_status()
```

- Retrieves the button status of the Mini Encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_get_counter_value.svg">

```python
hat_mini_encoderc_0.get_counter_value()
```

- Retrieves the current counter value of the encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_get_device_status.svg">

```python
hat_mini_encoderc_0.get_device_status()
```

- Checks the device status of the Mini Encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_get_increment_value.svg">

```python
hat_mini_encoderc_0.get_increment_value()
```

- Retrieves the increment value since the last check.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_reset_counter_value.svg">

```python
hat_mini_encoderc_0.reset_counter_value()
```

- Resets the encoder counter value to zero.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_set_counter_value.svg">

```python
hat_mini_encoderc_0.set_counter_value(0)
```

- Sets the encoder counter value to a specified value, here set to `0`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_set_i2c_address.svg">

```python
hat_mini_encoderc_0.set_i2c_address(new_address)
```

- Changes the I2C address of the Mini Encoder to `new_address`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/mini_encoderc/uiflow_block_hat_miniencoderc_set_led_rgb.svg">

```python
hat_mini_encoderc_0.set_LED_RGB24(red, green, blue)
```

- Sets the RGB LED color of the Mini Encoder by specifying the red, green, and blue values.