# [Unit UWB](/en/unit/uwb)

## Example

The Anchor mode is used to fix as an anchor point

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_example01.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
uwb_0 = unit.get(unit.UWB, unit.PORTC)

uwb_0.init_uwb_mode(0)
uwb_0.set_mode(0)
while True:
  if uwb_0.check_device:
    print((str('distance') + str((uwb_0.device_id))))
  wait_ms(2)
```

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_example02.svg">

Tag mode, move points, get positioning

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
uwb_0 = unit.get(unit.UWB, unit.PORTC)

uwb_0.init_uwb_mode()
uwb_0.set_mode()
while True:
  if uwb_0.check_device:
    print((str('distance') + str((uwb_0.get_distance_measure[0]))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_init.svg">

```python
uwb_0.init_uwb_mode()
```

- Initializes Unit and sets the running mode
  - tag: indicates the tag mode
  - Anchor: indicates the anchor mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_uart_init.svg">

```python
uwb_0.uart_port_id(1)
```

- Set the component ID number

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_check_device.svg">

```python
print(uwb_0.check_device)
```

- Check whether the device is available

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_continuous_value_output.svg">

```python
uwb_0.continuous_output_value(0)
```

- Continuous value output output
  - Enable
  - Disable

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_get_device_id.svg">

```python
print(uwb_0.device_id)
```

- Get device ID

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_get_distance_measure.svg">

```python
print(uwb_0.get_distance_measure[0])
```

- Get the distance to the anchor point

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_get_version.svg">

```python
print(uwb_0.get_version())
```

- Obtain the current firmware version

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_set_anchor.svg">

```python
uwb_0.set_mode(0)
```

- Set the anchor mode ID value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_set_interval.svg">

```python
uwb_0.set_range_interval(5)
```

- Set the interval for obtaining data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_set_tag.svg">

```python
uwb_0.set_mode()
```

- Set label mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/uwb/uiflow_block_unit_uwb_update_value_loop.svg">

```python
uwb_0.update_new_value_loop()
```

- Update distance value

