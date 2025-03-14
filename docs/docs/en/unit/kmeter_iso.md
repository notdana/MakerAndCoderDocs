# [Unit KMeter-ISO](/en/unit/KMeterISO%20Unit)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
KMeterISO_0 = unit.get(unit.KMETER_ISO, unit.PORTA)

KMeterISO_0.init_i2c_address(0x66)
print((str('Version:') + str((KMeterISO_0.get_firmware_version()))))
print((str('I2C address:') + str((KMeterISO_0.rw_i2c_address()))))
while True:
  print((str('thermocouple::') + str((KMeterISO_0.get_kmeter_thermo(1)))))
  print((str('internal:') + str((KMeterISO_0.get_kmeter_internal(1)))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_init_i2c.svg">

```python
KMeterISO_0.init_i2c_address(0x66)
```

- Initializes the i2c address of the device. The default is 0x66

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_fw_version.svg">

```python
print(KMeterISO_0.get_firmware_version())
```

- Obtain the firmware version of the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_i2c_address.svg">

```python
print(KMeterISO_0.rw_i2c_address())
```

- Obtain the i2c address of the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_internal_temp.svg">

```python
print(KMeterISO_0.get_kmeter_internal(1))
```

- Get the internal temperature of the chip (Celsius or Fahrenheit)
  - CELSIUS
  - FAHRENHEIT

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_isready.svg">

```python
print(KMeterISO_0.get_isready())
```

- Set the device to start measuring temperature

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_str_internal_temp.svg">

```python
print(KMeterISO_0.get_kmeter_internal_string(1))
```

- Output the chip temperature as a string
  - CELSIUS
  - FAHRENHEIT

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_str_thermo_temp.svg">

```python
print(KMeterISO_0.get_kmeter_thermo_string(1))
```

- Output the temperature of the thermocouple as a string
  - CELSIUS
  - FAHRENHEIT

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_get_thermo_temp.svg">

```python
print(KMeterISO_0.get_kmeter_thermo(1))
```

- Get thermocouple temperature
  - CELSIUS
  - FAHRENHEIT

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter_iso/uiflow_block_unit_kmeteriso_set_i2c_address.svg">

```python
KMeterISO_0.rw_i2c_address(0x66)
```

- Set the i2c address of the device

