# Module13.2 2Relay

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x000000)
relay2 = module.get(module.RELAY2)

relay2.init_i2c_address(0x25)
print((str('DEVICE VER:') + str((relay2.read_status(0xFE)))))
print((str('DEVICE I2C:') + str((relay2.read_status(0xFF)))))
while True:
  relay2.write_relay_state(1, 0)
  relay2.write_relay_state(2, 0)
  wait(1)
  relay2.write_relay_state(1, 1)
  relay2.write_relay_state(2, 1)
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_init.svg">

```python
import module
relay2 = module.get(module.RELAY2)
relay2.init_i2c_address(0x25)
```

- Initialize the module and specify the I2C address (default is 0x25).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_get_info.svg">

```python
print(relay2.read_status(0xFE))
```

- Get device firmware version information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_set_state.svg">

```python
relay2.write_relay_state(1, 1)
```

- Setting Relay Status:
  - relay: 1-2
  - state:
    - on:1
    - off:0

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_get_status.svg">

```python
print(relay2.read_relay_status(1))
```

- Read relay status:
  - relay: 1-2
- return
  - state:
    - on:1
    - off:0


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/2relay/uiflow_block_module_relay2_set_address.svg">

```python
relay2.write_i2c_address(0x25)
```

- Setting the module I2C address
