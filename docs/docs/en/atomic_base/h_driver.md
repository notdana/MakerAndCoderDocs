# Atomic HDriver Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/h_driver/uiflow_block_hdriver_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.HDriver import HDriver
import time

hdriver = HDriver()
print((str('Input Voltage: ') + str((hdriver.get_voltage()))))
while True:
  print((str('Motor Fault Status: ') + str((hdriver.get_status()))))
  hdriver.set_speed(100)
  wait(1)
  hdriver.set_speed(0)
  wait(1)
  hdriver.set_speed(-100)
  wait(1)
  hdriver.set_speed(0)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/h_driver/uiflow_block_hdriver_init.svg">

```python
from base.HDriver import HDriver
hdriver = HDriver()
```

- Initialize Atomic H-Driver.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/h_driver/uiflow_block_hdriver_get_status.svg">

```python
hdriver.get_status()
```

- Get the current operating status:
  - 0: Fault
  - 1: OK

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/h_driver/uiflow_block_hdriver_get_voltage.svg">

```python
hdriver.get_voltage()
```

- Read the input voltage value (V).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/h_driver/uiflow_block_hdriver_set_speed.svg">

```python
hdriver.set_speed(100)
```

- Control motor speed:
  - Input range: -100 to +100, with 0 to stop.

