# [Unit Accel](/en/unit/accel)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/accel/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
accel_0 = unit.get(unit.ACCEL, unit.PORTA)

while True:
  print((str('X ACC:') + str((accel_0.acceleration[0]))))
  print((str('Y ACC:') + str((accel_0.acceleration[1]))))
  print((str('Z ACC:') + str((accel_0.acceleration[2]))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/accel/uiflow_block_unit_accel_get_x_acc.svg">

```python
print((str('X ACC:') + str((accel_0.acceleration[0]))))
```

- Get the X acceleration value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/accel/uiflow_block_unit_accel_get_y_acc.svg">

```python
print((str('Y ACC:') + str((accel_0.acceleration[1]))))
```

- Get the Y acceleration value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/accel/uiflow_block_unit_accel_get_z_acc.svg">

```python
print((str('Z ACC:') + str((accel_0.acceleration[2]))))
```

- Get the Z acceleration value

