# [Unit Watering](/en/unit/watering)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/watering/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
Watering_0 = unit.get(unit.WATERING, unit.PORTB)

while True:
  print((str('Water: ') + str((Watering_0.get_adc_value()))))
  if (Watering_0.get_adc_value()) < 1000:
    Watering_0.set_pump_status(1)
  else:
    Watering_0.set_pump_status(0)
  wait(0.3)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/watering/uiflow_block_watering_get_adc_value.svg">

```python
print(Watering_0.get_adc_value())
```

- Gets the raw ACD value of the Unit test

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/watering/uiflow_block_watering_set_pump_status.svg">

```python
Watering_0.set_pump_status(0)
```

- The state of the pump is set by variable 0/1 (ON/OFF)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/watering/uiflow_block_watering_set_pump_status_dropdown.svg">

```python
Watering_0.set_pump_status(0)
```

- Set the water pump status
  - ON
  - OFF



