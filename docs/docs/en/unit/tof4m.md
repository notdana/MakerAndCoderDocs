# [Unit ToF4M](/en/unit/Unit-ToF4M)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof4m/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
tof4m_0 = unit.get(unit.TOF4M, unit.PORTA)

tof4m_0.set_distance_mode('SHORT')
tof4m_0.set_measurement_timing_budget(200)
while True:
  print(tof4m_0.get_single_distance_value)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof4m/uiflow_block_unit_tof4m_get_single_distance.svg">

```python
print(tof4m_0.get_single_distance_value)
```

- Gets the individual distance measured by Unit ToF4M (returns int). Unit millimeter

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof4m/uiflow_block_unit_tof4m_set_distance_mode.svg">

```python
tof4m_0.set_distance_mode('SHORT')
```

- Set the measurement mode of Unit ToF4M
  - SHORT:indicates a short distance
  - MEDIUM:indicates the medium distance
  - LONG:indicates a long distance

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/tof4m/uiflow_block_unit_tof4m_set_measurement_budget.svg">

```python
tof4m_0.set_measurement_timing_budget(200)
```

- Set up Unit ToF4M Time Budget (ms)


