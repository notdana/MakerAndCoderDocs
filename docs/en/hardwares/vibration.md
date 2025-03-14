# Vibration

## Example

Set the vibration intensity and vibrate once every second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/vibration/uiflow_block_vibration_demo.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import time

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

power.setVibrationIntensity(255)
while True:
  power.setVibrationEnable(True)
  wait(1)
  power.setVibrationEnable(False)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/vibration/uiflow_block_vibration_set_motor_on.svg"> 

```python
power.setVibrationEnable(True)
```

- Turn on the motor vibration.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/vibration/uiflow_block_vibration_set_motor_off.svg"> 

```python
power.setVibrationEnable(False)
```
 
- Turn off the motor vibration.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/vibration/uiflow_block_vibration_set_motor_vibrate_time.svg"> 

```python
power.setVibrationEnable(True)
wait(2)
power.setVibrationEnable(False)
wait_ms(2)
```

- Set the vibration duration.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/vibration/uiflow_block_vibration_set_motor_vibrate_intensity.svg"> 

```python
power.setVibrationIntensity(255)
```

- Set the vibration intensity (0-255), where a larger value means a stronger vibration.