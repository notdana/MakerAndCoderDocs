# Unit Pbhub

## Example

Control Motor Rotation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
pbhub_0 = unit.get(unit.PBHUB, unit.PORTA)

while True:
  pbhub_0.setServoAngle(0, 0, 11)
  wait(1)
  pbhub_0.setServoAngle(0, 0, 180)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_init_i2c_address.svg">

```python
pbhub_0.init_i2c_address(0x61)
```

- Initialize I2C Address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_analogRead.svg">

```python
print(pbhub_0.analogRead(0))
```

- Read Analog Value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_digital_read_value.svg">

```python
print(pbhub_0.digitalRead(0, 0))
```

- Read Digital Value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_digital_write_value.svg">

```python
pbhub_0.digitalWrite(0, 0, 0)
```

- Write Digital Value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_pwm_read.svg">

```python
print(pbhub_0.pwmRead(0, 0))
```

- Read Pulse from Pin

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_pwm_write.svg">

```python
pbhub_0.pwmWrite(0, 0, 0)
```

- Write Pulse to Pin

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_read_status.svg">

```python
print(pbhub_0.read_status(0xFE))
```

- Read Unit Status/Version Number

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setBrightness_value.svg">

```python
pbhub_0.setBrightness(0, 50)
```

- Set RGB LED Brightness

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setColorPos_value.svg">

```python
pbhub_0.setColorPos(0, 0, 0xff0000)
```

- Set RGB LED Color

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setColorPos_value_input.svg">

```python
pbhub_0.setColorPos(0, 0, 0xff0000)
```

- Set Range of RGB LED Colors

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setColor_value.svg">

```python
pbhub_0.setColor(0, 0, 0, 0xff0000)
```

- 设置指定引脚对应指定范围RGB灯珠的颜色

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setColor_value_input.svg">

```python
pbhub_0.setColor(0, 0, 0, 0xff0000)
```

- Set Range of RGB LED Colors (Multiple Formats)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_setRgbNum_value.svg">

```python
pbhub_0.setRgbNum(0, 1)
```

- Set LED Light on Specified Pin

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_set_i2c_address.svg">

```python
pbhub_0.init_i2c_address(0x61)
```

- Set Firmware Version/I2C Address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_set_servo_angle.svg">

```python
pbhub_0.setServoAngle(0, 0, 90)
```

- Set Servo Motor Angle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/pbhub/uiflow_block_pbhub_set_servo_pulse.svg">

```python
pbhub_0.setServoPulse(0, 0, 1000)
```

- Write Digital Value (Duplicate)

