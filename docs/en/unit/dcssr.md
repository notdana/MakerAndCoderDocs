# Unit DCSSR

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x444444)
dcssr_0 = unit.get(unit.DC_SSR, unit.PORTA)

def buttonA_wasPressed():
  # global params
  dcssr_0.set_i2c_ssr_state(1)
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  dcssr_0.set_i2c_ssr_state(0)
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  # global params
  dcssr_0.set_i2c_rgb_led(50, 50, 50)
  pass
btnC.wasPressed(buttonC_wasPressed)

dcssr_0.init_mode(1)
print((str('FW version:') + str((dcssr_0.get_i2c_status(0xFE)))))
while True:
  if dcssr_0.get_i2c_ssr_status():
    print('ON')
  else:
    print('OFF')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_init_i2c_address.svg">

```python
dcssr_0.init_i2c_address(0x50)
```

- Initializes the I2C communication address of the DCSSR Unit

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_init_modbus.svg">

```python
dcssr_0.init_modbus(4, 1, 115200, 8, 1, None)
```

- Initializes the Modbus communication format

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_i2c_led.svg">

```python
print(dcssr_0.get_i2c_rgb_led())
```

- Get the RGB value through i2c

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_i2c_ssr_status.svg">

```python
print(dcssr_0.get_i2c_ssr_status())
```

- Obtain the switching status of the SSR through I2C

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_i2c_status.svg">

```python
print(dcssr_0.get_i2c_status(0xFE))
```

- Obtain the firmware version in I2C mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_modbus_led.svg">

```python
print(dcssr_0.get_modbus_rgb_led())
```

- Obtain the RGB value through Modbus communication

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_modbus_ssr_status.svg">

```python
print(dcssr_0.get_i2c_ssr_status())
```

- Obtain the switching status of the SSR over Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_get_modbus_status.svg">

```python
print(dcssr_0.get_modbus_ssr_status())
```

- Obtain the firmware version over Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_select_mode.svg">

```python
dcssr_0.init_mode(1)
```

- Set the communication mode of the DCSSR Unit, I2C or Modbus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_i2c_address.svg">

```python
dcssr_0.set_i2c_address(0x50)
```

- Set the i2c address of the DCSSR

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_i2c_rgb_led.svg">

```python
dcssr_0.set_i2c_rgb_led(50, 50, 50)
```

- Set the RGB value using i2c

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_i2c_ssr_state.svg">

```python
dcssr_0.set_i2c_ssr_state(1)
```

- Set the switch status of the SSR device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_modbus_address.svg">

```python
dcssr_0.set_modbus_address(0x50)
```

- Set the i2c address of the DCSSR

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_modbus_rgb_led.svg">

```python
dcssr_0.set_modbus_rgb_led(50, 50, 50)
```

- Modbus Sets the RGB value of the LED

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/dcssr/uiflow_block_unit_dcssr_set_modbus_ssr_state.svg">

```python
dcssr_0.set_modbus_ssr_state(1)
```

- Modbus Sets the status switch of the SSR



