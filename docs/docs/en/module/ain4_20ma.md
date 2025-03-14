# Module13.2 AIN4-20mA

## Example

#> Get the adc value, the current value and the firmware version of the four channels


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_AIN4-20mA_demo1.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

setScreenColor(0x222222)

ain420 = module.get(module.AIN_420MA)

ain420.init_i2c_address(0x55)
while True:
  print((str('ADC1 Value:') + str((ain420.get_adc_raw16_value(1)))))
  print((str('ADC2 Value:') + str((ain420.get_adc_raw16_value(1)))))
  print((str('ADC3 Value:') + str((ain420.get_adc_raw16_value(1)))))
  print((str('ADC4 Value:') + str((ain420.get_adc_raw16_value(1)))))
  print((str('Current:') + str((ain420.get_ain_current_value(1)))))
  print((str('Firmware version:') + str((ain420.get_firmware_status()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_module_ain420ma_get_adc_raw16_value.svg">

```python
ain420.get_adc_raw16_value(1)
```

- Retrieves the 16-bit ADC raw value of the specified channel. This is an unprocessed digital signal representation read from the specified channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_module_ain420ma_get_current_value.svg">

```python
ain420.get_ain_current_value(1)
```

- Retrieves the current value of the specified channel. This is typically used to read data from current sensors, indicating the actual current value on the channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_module_ain420ma_get_firmware_version.svg">

```python
ain420.get_firmware_status()
```

- Retrieves the firmware version number of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_module_ain420ma_init.svg">

```python
ain420.init_i2c_address(0x55)
```

- Initializes the I2C address of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/ain4_20ma/uiflow_block_module_ain420ma_set_i2c_address.svg">

```python
ain420.set_i2c_address(0x55)
```

- Sets the I2C slave address of the device.