# [Unit ExtEncoder](/en/unit/ExtEncoder%20Unit)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
extencoder_0 = unit.get(unit.EXT_ENCODER, unit.PORTA)

extencoder_0.init_i2c_address(0x59)
while True:
  print((str('encoder:') + str((extencoder_0.get_encoder_value()))))
  print((str('meter:') + str((extencoder_0.get_meter_value()))))
  print((str('string meter') + str((extencoder_0.get_str_meter_value()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_init.svg">

```python
extencoder_0.init_i2c_address(0x59)
```

- Create an ExtEncoderUnit object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_device_firmware.svg">

```python
print(extencoder_0.get_firmware_status())
```

- Retrieve the firmware version of the ExtEncoderUnit object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_encoder_value.svg">

```python
print(extencoder_0.get_encoder_value())
```

- Get the encoder pulse count value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_meter_value.svg">

```python
print(extencoder_0.get_meter_value())
```

- Get the meter value of the ExtEncoderUnit object. Unit: millimeters

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_perimeter_value.svg">

```python
print(extencoder_0.get_perimeter_value())
```

- Get the circumference of the ExtEncoderUnit object. Unit: millimeters

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_pulse_value.svg">

```python
print(extencoder_0.get_pulse_value())
```

- Get the pulses per revolution value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_str_meter_value.svg">

```python
print(extencoder_0.get_str_meter_value())
```

- Get the string representation of the meter pulse count value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_zero_counter_value.svg">

```python
print(extencoder_0.get_zero_counter_value())
```

- Get the zero mode of the ExtEncoderUnit object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_get_z_trigger_mode.svg">

```python
print(extencoder_0.get_z_trigger_mode())
```

- Transition to Z-trigger mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_reset_encoder.svg">

```python
extencoder_0.reset_encoder()
```

- Reset the encoder and meter count values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_set_i2c_address.svg">

```python
extencoder_0.set_i2c_address(0x59)
```

- Set the device I2C slave address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_set_perimeter_value.svg">

```python
extencoder_0.set_perimeter_value(1000)
```

- Set peripheral values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_set_pulse_value.svg">

```python
extencoder_0.set_pulse_value(1000)
```

- Set the pulses per revolution value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_set_zero_counter_value.svg">

```python
extencoder_0.set_zero_counter_value(0)
```

- Set the total zero pulse value for the object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ext_encoder/uiflow_block_unit_extencoder_set_z_trigger_mode.svg">

```python
extencoder_0.set_z_trigger_mode(0)
```

- Set the clear Z-trigger mode
  - NOT CLEAR
  - Z-RISING EDGE
  - Z-FALLING EDGE

