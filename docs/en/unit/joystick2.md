# [Unit Joystick2](/en/unit/Unit-JoyStick2)

## Example

> Initialize the joystick module's I2C address and LED brightness, then continuously fetch the joystick's current position, ADC values, button status, and firmware version in a loop and print them.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/uiflow_block_unit_joystick2_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

joystick2_0 = unit.get(unit.JOYSTICKV2, unit.PORTA)

joystick2_0.init_i2c_address(0x63)
joystick2_0.set_led_brightness(50)
while True:
  print(joystick2_0.get_axis_position())
  print(joystick2_0.get_x_position())
  print(joystick2_0.get_y_position())
  print(joystick2_0.get_adc_value())
  print(joystick2_0.get_x_raw())
  print(joystick2_0.get_y_raw())
  print(joystick2_0.get_button_status())
  print(joystick2_0.get_firmware_version())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/1_uiflow_block_unit_joystick2_init.svg">

```python
joystick2_0.init_i2c_address(0x63)
```

- Set the joystick module's I2C address. Address range is 0x08 to 0x77, default value is 0x63.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/2_uiflow_block_unit_joystick2_get_axis_position.svg">

```python
joystick2_0.get_axis_position()
```

- Get the joystick's current position (X and Y coordinates), returns a tuple.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/3_uiflow_block_unit_joystick2_get_x_position.svg">

```python
joystick2_0.get_x_position()
```

- Get the joystick's X-axis position value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/4_uiflow_block_unit_joystick2_get_y_position.svg">

```python
joystick2_0.get_y_position()
```

- Get the joystick's Y-axis position value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/5_uiflow_block_unit_joystick2_get_adc_value.svg">

```python
joystick2_0.get_adc_value()
```

- Get the joystick's X and Y axes' ADC values (analog values), returns a tuple.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/6_uiflow_block_unit_joystick2_get_x_raw.svg">

```python
joystick2_0.get_x_raw()
```

- Get the joystick's X-axis ADC value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/7_uiflow_block_unit_joystick2_get_y_raw.svg">

```python
joystick2_0.get_y_raw()
```

- Get the joystick's Y-axis ADC value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/8_uiflow_block_unit_joystick2_get_button_status.svg">

```python
joystick2_0.get_button_status()
```

- Get the joystick button's status. Returns `True` if pressed; otherwise `False`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/9_uiflow_block_unit_joystick2_get_firmware_version.svg">

```python
joystick2_0.get_firmware_version()
```

- Get the joystick module's firmware version, returns an integer value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/10_uiflow_block_unit_joystick2_set_axis_x_invert.svg">

```python
joystick2_0.set_axis_x_invert(True)
```

- Invert the X-axis direction. When set to `True`, the X-axis output value will be reversed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/11_uiflow_block_unit_joystick2_set_axis_y_invert.svg">

```python
joystick2_0.set_axis_y_invert(True)
```

- Invert the Y-axis direction. When set to `True`, the Y-axis output value will be reversed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/12_uiflow_block_unit_joystick2_set_axis_swap.svg">

```python
joystick2_0.set_axis_swap(True)
```

- Swap the X and Y axes' output values. When set to `True`, the X and Y axis data will be exchanged.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/13_uiflow_block_unit_joystick2_set_deadzone_position.svg">

```python
joystick2_0.set_deadzone_position(0, 0)
```

- Set the joystick's position deadzone range. Values within the deadzone will be treated as the center position to avoid noise. Parameter range: 0 to 4096.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/14_uiflow_block_unit_joystick2_set_deadzone_adc.svg">

```python
joystick2_0.set_deadzone_adc(0, 0)
```

- Set the joystick's ADC value deadzone range. Parameter range: 0 to 32768.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/15_uiflow_block_unit_joystick2_fill_color.svg">

```python
joystick2_0.fill_color(0xff0000)
```

- Set the joystick LED's fill color (such as the indicator light color on the module).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/16_uiflow_block_unit_joystick2_set_led_brightness.svg">

```python
joystick2_0.set_led_brightness(50)
```

- Set the joystick LED's brightness, range: 0% to 100%.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/17_uiflow_block_unit_joystick2_set_address.svg">

```python
joystick2_0.set_i2c_address(0x63)
```

- Change the joystick module's I2C address. Used to avoid address conflicts in a multi-module environment.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/18_uiflow_block_unit_joystick2_set_axis_x_mapping.svg">

```python
joystick2_0.set_axis_x_mapping(0, 0, 0, 0)
```

- Set the X-axis mapping parameters:
  - Min negative ADC value: Minimum negative ADC value for the X-axis (farthest left or bottom).
  - Max negative ADC value: Maximum negative ADC value for the X-axis.
  - Min positive ADC value: Minimum positive ADC value for the X-axis (farthest right or top).
  - Max positive ADC value: Maximum positive ADC value for the X-axis.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/joystick2/19_uiflow_block_unit_joystick2_set_axis_y_mapping.svg">

```python


joystick2_0.set_axis_y_mapping(0, 0, 0, 0)
```

- Set the Y-axis mapping parameters:
  - Min negative ADC value: Minimum negative ADC value for the Y-axis (farthest left or bottom).
  - Max negative ADC value: Maximum negative ADC value for the Y-axis.
  - Min positive ADC value: Minimum positive ADC value for the Y-axis (farthest right or top).
  - Max positive ADC value: Maximum positive ADC value for the Y-axis.