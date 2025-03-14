# Unit DigiClock

## Example

Numeral display character A

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
digi_clock_0 = unit.get(unit.DIGI_CLOCK, unit.PORTA)

digi_clock_0.init_i2c_address(0x30)
digi_clock_0.write_brightness(4)
while True:
  digi_clock_0.write_char('A',0)
  wait(1)
  digi_clock_0.clear()
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_init_i2c_address.svg">

```python
igi_clock_0.init_i2c_address(0x30)
```

- Initialize I2C address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_clear.svg">

```python
digi_clock_0.clear()
```

- Clear display data on digital screen

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_read_version.svg">

```python
print(digi_clock_0.read_version())
```

- Retrieve Unit version

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_write_brightness.svg">

```python
digi_clock_0.write_brightness(0)
```

- Set screen brightness

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_write_char.svg">

```python
digi_clock_0.write_char('',0)
```

- Display a character on a specific index of the digital tube

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_write_char_list.svg">

```python
digi_clock_0.write_char_list('')
```

- Display a string on a specific index of the digital tube

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_write_match_string.svg">

```python
digi_clock_0.write_match_string('')
```

- Display a numeric string on the digital tubes. For example, "12356"

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/digi_clock/uiflow_block_unit_digiclock_write_raw.svg">

```python
digi_clock_0.write_raw(0,0)
```

- Write raw data to a specified digital tube

