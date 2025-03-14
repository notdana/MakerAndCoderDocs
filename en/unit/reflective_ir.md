# Unit Reflective IR

## Example

<img class="blockly_svg" src="example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
reflective_ir_0 = unit.get(unit.REFLECTIVE_IR, unit.PORTB)

while True:
  print((str('analog:') + str((reflective_ir_0.get_analog_output()))))
  print((str('digital:') + str((reflective_ir_0.get_digital_output()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/reflective_ir/uiflow_block_unit_reflectiveir_get_analog_output.svg">

```python
print(reflective_ir_0.get_analog_output())
```

- Reads the ADC value of the reflected IR unit and returns an integer value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/reflective_ir/uiflow_block_unit_reflectiveir_get_digital_output.svg">

```python
print(reflective_ir_0.get_digital_output())
```

- Reads the numeric value of the reflected IR unit and returns an integer value

