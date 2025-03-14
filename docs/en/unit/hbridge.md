# [Unit HBridge](/en/unit/Hbridge%20Unit)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
hbridge_0 = unit.get(unit.HBRIDGE, unit.PORTA)

hbridge_0.init_i2c_address(0x20)
hbridge_0.set_8bit_pwm(127)
hbridge_0.set_16bit_pwm(32767)
hbridge_0.set_direction(1)
while True:
  print((str('Current:') + str(((str((hbridge_0.get_vin_current())) + str('A'))))))
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_init.svg">

```python
hbridge_0.init_i2c_address(0x20)
```

- Initializes Unit and sets the I2C address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_get_adc_value.svg">

```python
print(hbridge_0.get_adc_value(0, 8))
```

- Get voltage resolution

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_get_current.svg">

```python
print(hbridge_0.get_vin_current())
```

- Get voltage (A, Float)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_get_device_status.svg">

```python
print(hbridge_0.get_device_status(0xFE))
```

- Get the Unit version

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_get_driver_config.svg">

```python
print(hbridge_0.get_driver_config(4))
```

- Obtain configuration information
  - DIRECTION
  - 8Bit_PWM_DUTY
  - 16Bit_PWM_DUTY
  - PWM_FREQUENCY

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_set_16bit_pwm.svg">

```python
hbridge_0.set_16bit_pwm(32767)
```

- Set the 16-bit PWM duty cycle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_set_8bit_pwm.svg">

```python
hbridge_0.set_8bit_pwm(127)
```

- Set the 8-bit PWM duty cycle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_set_direction.svg">

```python
hbridge_0.set_direction(0)
```

- Set the current direction
 - STOP
 - FORWARD
 - REVERSE

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/hbridge/uiflow_block_unit_hbridge_set_pwm_freq.svg">

```python
hbridge_0.set_pwm_freq(1000)
```

- Set the PWM frequency

