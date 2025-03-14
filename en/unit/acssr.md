# Unit ACSSR

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
acssr_0 = unit.get(unit.AC_SSR, unit.PORTA)

def buttonA_wasPressed():
  # global params
  acssr_0.set_i2c_ssr_state(1)
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  acssr_0.set_i2c_ssr_state(0)
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  # global params
  acssr_0.set_i2c_rgb_led(50, 50, 50)
  pass
btnC.wasPressed(buttonC_wasPressed)

acssr_0.init_mode(1)
print((str('FW version:') + str((acssr_0.get_i2c_status(0xFE)))))
while True:
  if acssr_0.get_i2c_ssr_status():
    print('ON')
  else:
    print('OFF')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_init_i2c_address.svg">

```python
acssr_0.init_i2c_address(0x50)
```

- Initializes the I2C communication address of the ACSSR Unit

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_init_modbus.svg">

```python
acssr_0.init_modbus(4, 1, 115200, 8, 1, None)
```

- Initializes the Modbus communication format

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_i2c_led.svg">

```python
print(acssr_0.get_i2c_rgb_led())
```

- Get the RGB value through i2c

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_i2c_ssr_status.svg">

```python
print(acssr_0.get_i2c_ssr_status())
```

- Obtain the switching status of the SSR through I2C

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_i2c_status.svg">

```python
print(acssr_0.get_i2c_status(0xFE))
```

- Obtain the firmware version in I2C mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_modbus_led.svg">

```python
print(acssr_0.get_modbus_rgb_led())
```

- Obtain the RGB value through Modbus communication

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_modbus_ssr_status.svg">

```python
print(acssr_0.get_modbus_ssr_status())
```

- Obtain the switching status of the SSR over Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_get_modbus_status.svg">

```python
print(acssr_0.get_modbus_status(0x0001))
```

- Obtain the firmware version over Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_select_mode.svg">

```python
acssr_0.init_mode(1)
```

- Set the communication mode of the ACSSR Unit, I2C or Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_i2c_address.svg">

```python
acssr_0.set_i2c_address(0x50)
```

- Set the i2c address of the ACSSR

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_i2c_rgb_led.svg">

```python
acssr_0.set_i2c_rgb_led(50, 50, 50)
```

- Set the RGB value using i2c

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_i2c_ssr_state.svg">

```python
acssr_0.set_i2c_ssr_state(1)
```

- Set the switch status of the SSR device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_modbus_address.svg">

```python
acssr_0.set_modbus_address(0x50)
```

- Set the i2c address of the ACSSR

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_modbus_rgb_led.svg">

```python
acssr_0.set_modbus_rgb_led(50, 50, 50)
```

- Modbus Sets the RGB value of the LED

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/acssr/uiflow_block_unit_acssr_set_modbus_ssr_state.svg">

```python
acssr_0.set_modbus_ssr_state(1)
```

- Modbus Sets the status switch of the SSR
