# Module 4Encoder Motor

## Example

#> The four coded clicks set different pwm values, control different speeds and directions, and print out input voltage values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_4encoder_demo2.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import module

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

encoder4_motor = module.get(module.ENCODER4MOTOR)

encoder4_motor.init_i2c_address(0x24)
encoder4_motor.set_all_motors_mode(0x00)
while True:
  encoder4_motor.set_motor_pwm_dutycycle(0x00, (-127))
  encoder4_motor.set_motor_pwm_dutycycle(0x01, 50)
  encoder4_motor.set_motor_pwm_dutycycle(0x02, 95)
  encoder4_motor.set_motor_pwm_dutycycle(0x03, 127)
  print((str('Vin value:') + str((encoder4_motor.get_vin_current_int_value()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_device_spec.svg">

```python
encoder4_motor.get_device_spec(0xFE)
```

- Retrieves the firmware version information of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_encoder_mode_direction.svg">

```python
encoder4_motor.get_encoder_mode()
```

- Retrieves the direction information of the encoder mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_motor_encoder_value.svg">

```python
encoder4_motor.get_motor_encoder_value(0x00)
```

- Retrieves the encoder value of the specified motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_motor_pos_pid_value.svg">

```python
encoder4_motor.get_position_PID_value(0x00)
```

- Retrieves the position control PID values of the specified motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_motor_speed_pid_value.svg">

```python
encoder4_motor.get_speed_PID_value(0x00)
```

- Retrieves the speed control PID values of the specified motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_motor_speed_value.svg">

```python
encoder4_motor.get_motor_speed_value(0x00)
```

- Retrieves the current speed value of the specified motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_vin_adc_raw12_value.svg">

```python
encoder4_motor.get_vin_adc_raw12_value()
```

- Retrieves the 12-bit ADC (Analog-to-Digital Conversion) raw value of the input voltage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_vin_adc_raw8_value.svg">

```python
encoder4_motor.get_vin_adc_raw8_value()
```

- Retrieves the 8-bit ADC (Analog-to-Digital Conversion) raw value of the input voltage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_vin_current_float_value.svg">

```python
encoder4_motor.get_vin_current_float_value()
```

- Retrieves the input voltage current value in amperes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_vin_current_value.svg">

```python
encoder4_motor.get_vin_current_int_value()
```

- Retrieves the input voltage current value in milliamps.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_get_vin_voltage_value.svg">

```python
encoder4_motor.get_vin_voltage()
```

- Retrieves the voltage value of the input voltage, returning an integer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_init.svg">

```python
encoder4_motor.init_i2c_address(0x24)
```

- Initializes the I2C address of the device, ranging from 0x01 to 0x7F.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_encoder_mode_direction.svg">

```python
encoder4_motor.set_encoder_mode(0x00)
```

- Sets the direction of the encoder mode, with options for "AB" or "BA" mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_i2c_address.svg">

```python
encoder4_motor.set_i2c_address(0x24)
```

- Sets the I2C address of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_mode.svg">

```python
encoder4_motor.set_motor_mode(0x00, 0x00)
```

- Sets the running mode of motor 1. The drop-down menu provides three options:
  - NORMAL: Normal mode, where the motor operates according to default settings.
  - POSITION: Position control mode, controlling the motor movement by specifying a position.
  - SPEED: Speed control mode, controlling the motor rotation by specifying a speed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_mode_all.svg">

```python
encoder4_motor.set_all_motors_mode(0x00)
```

- Sets the mode for all motors:
  - NORMAL: Normal mode, where motors operate according to default settings.
  - POSITION: Position control mode, controlling motor movement by specifying positions.
  - SPEED: Speed control mode, controlling motor rotation by specifying speeds.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_motor_encoder_value.svg">

```python
encoder4_motor.set_motor_encoder_value(0x00, 1000)
```

- Sets the encoder value for the motor, which typically represents the current position or cumulative rotation of the motor.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_pos_encoder_value.svg">

```python
encoder4_motor.set_position_encoder_value(0x00, 1000)
```

- Sets the position encoder value for the motor. This value is used to specify the target position or current position in position control mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4encoder_motor/uiflow_block_module_4encodermotor_set_pos_max_speed_value.svg">

```python
encoder4_motor.set_position_max_speed_value(0x00, 100)
```

- Sets the maximum speed value in position control mode, ranging from -127 to 127.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs