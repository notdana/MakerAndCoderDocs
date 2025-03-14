# Hat BugC2

## Example

> Alternates between moving forward and backward.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_bugc2_0 = hat.get(hat.BUGC2)

hat_bugc2_0.InitDeviceAddr(0x38)
while True:
  hat_bugc2_0.SetMotorSpeed(0x00, 100)
  hat_bugc2_0.SetMotorSpeed(0x02, 100)
  hat_bugc2_0.SetMotorSpeed(0x01, -100)
  hat_bugc2_0.SetMotorSpeed(0x03, -100)
  wait(5)
  hat_bugc2_0.SetMotorSpeed(0x00, -100)
  hat_bugc2_0.SetMotorSpeed(0x02, -100)
  hat_bugc2_0.SetMotorSpeed(0x01, 100)
  hat_bugc2_0.SetMotorSpeed(0x03, 100)
  wait(5)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_init.svg">

```python
hat_bugc2_0.InitDeviceAddr(0x38)
```

- Initialize the device I2C address, set to 0x38.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_get_adc_raw_value.svg">

```python
hat_bugc2_0.GetAdcValue(8)
```

- Get the raw 8-bit ADC value (returns an integer).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_get_bat_voltage.svg">

```python
hat_bugc2_0.GetBatVoltage
```

- Get the battery voltage in millivolts (returns an integer).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_get_device_spec.svg">

```python
hat_bugc2_0.GetDeviceSpec(0xFE)
```

- Retrieve detailed firmware version information (returns an integer).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_rx_cb.svg">

```python
hat_bugc2_0.SetRxCb(hat_bugc2_0_rx_cb)
```

- NEC infrared reception callback function, used to process received data and address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_set_i2c_address.svg">

```python
hat_bugc2_0.SetI2cAddress(0x38)
```

- Set the I2C address of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_set_motor_speed.svg">

```python
hat_bugc2_0.SetMotorSpeed(0x00, 50)
```

- Set the speed of the front-left motor. The current speed is set to 50, with a range of -100 to 100.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/bugc2/uiflow_block_hat_bugc2_set_rgb_color.svg">

```python
hat_bugc2_0.SetRGBColor(0x00, 0xff0000)
```

- Set the RGB color of the wheel lights, currently set to red.