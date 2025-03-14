# Hat CBack Driver

## Example

> Controls two servo channels to rotate back and forth from 0 to 180 degrees.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_cback_driver_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_cback_0 = hat.get(hat.CBACK)

while True:
  hat_cback_0.set_servo_angle(0x00, 0)
  hat_cback_0.set_servo_angle(0x01, 0)
  wait(1)
  hat_cback_0.set_servo_angle(0x00, 90)
  hat_cback_0.set_servo_angle(0x01, 90)
  wait(1)
  hat_cback_0.set_servo_angle(0x00, 180)
  hat_cback_0.set_servo_angle(0x01, 180)
  wait(1)
  hat_cback_0.set_servo_angle(0x00, 90)
  hat_cback_0.set_servo_angle(0x01, 90)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_cback_get_input.svg">

```python
hat_cback_0.set_output(0)
```

- Checks the status of input port B.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_cback_raw_adc.svg">

```python
hat_cback_0.get_adc16_raw()
```

- Reads the raw ADC value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_set_output.svg">

```python
hat_cback_0.set_output(0)
```

- Sets the status of output port B, with possible output values of 0 or 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_set_servo_angle.svg">

```python
hat_cback_0.set_servo_angle(0x00, 0)
```

- Sets the servo motor angle, specifying the servo channel (Channel 1 here) with an angle of 0 degrees.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/cback_driver/uiflow_block_hat_set_servo_pulse.svg">

```python
hat_cback_0.set_servo_pulse(0x10, 500)
```

- Sets the pulse width for the servo motor, specifying the servo channel (Channel 1 here) with a pulse width of 500.