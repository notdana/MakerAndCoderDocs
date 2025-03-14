# [Unit Heart](/en/unit/heart)

## Example

Output heart rate and blood oxygen data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/heart/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
heart_0 = unit.get(unit.HEART, unit.PORTA)

heart_0.setLedCurrent(0x04, 0x01)
heart_0.setMode(0x03)
while True:
  print((str('heart rate:') + str((heart_0.getHeartRate()))))
  print((str('spo2') + str((heart_0.getSpO2()))))
  wait(0.3)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/heart/uiflow_block_heart_get_heartrate.svg">

```python
print(heart_0.getHeartRate())
```

- Get heart rate

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/heart/uiflow_block_heart_get_spo2.svg">

```python
print(heart_0.getSpO2())
```

- Get SpO2

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/heart/uiflow_block_heart_set_led_current.svg">

```python
heart_0.setLedCurrent(0x00, 0x00)
```

- Set led current

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/heart/uiflow_block_heart_set_mode.svg">

```python
heart_0.setMode(0x02)
```

- Set the mode of HeartUnit
  - Heart Rate
  - Heart Rate with SpO2

