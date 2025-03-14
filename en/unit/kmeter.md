# [Unit KMeter]((/en/unit/kmeter))

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
KMeter_0 = unit.get(unit.KMETER, unit.PORTA)

KMeter_0.init_i2c_address(0x66)
print((str('firmware version:') + str((KMeter_0.get_firmware_version()))))
print((str('I2C address') + str((KMeter_0.rw_i2c_address()))))
while True:
  print((str('thermocouple:') + str((KMeter_0.get_kmeter(1)))))
  print((str('Internal Temp:') + str((KMeter_0.get_kmeter(2)))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_init_i2c.svg">

```python
KMeter_0.init_i2c_address(0x66)
```

- Initializes the i2c address of the device. The default is 0x66

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_get_fw_version.svg">

```python
print(KMeter_0.get_firmware_version())
```

- Obtain the firmware version of the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_get_i2c_address.svg">

```python
print(KMeter_0.rw_i2c_address())
```

- Obtain the i2c address of the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_get_sleep_time.svg">

```python
print(KMeter_0.rw_sleep_time())
```

- Get device sleep time

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_get_temperature.svg">

```python
print(KMeter_0.get_kmeter(1))
```

- Obtain the collection temperature
  - Thermocouple
  - Internal Temp

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_set_i2c_address.svg">

```python
KMeter_0.rw_i2c_address(0x66)
```

- Set the i2c address of the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_set_sleep_time.svg">

```python
KMeter_0.rw_sleep_time(5)
```

- Set device sleep time

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/kmeter/uiflow_block_kmeter_set_wake_up_mode.svg">

```python
KMeter_0.set_wakeup_timer(True)
```

- Set device sleep time

