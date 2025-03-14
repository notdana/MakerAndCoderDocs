# Module COMX Zigbee

## Example

The following example demonstrates a network composed of a Coordinator and an End Device for data transmission and reception.

### Coordinator


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_coordinator_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from comx.zigbee import Zigbee
import time

setScreenColor(0x222222)
zigbee = Zigbee(17, 16)
zigbee.set_param_module(1, 0x1617, 20, 1, 0x2345, 6, 1, '')
while True:
  zigbee.send_payload('Hello!')
  print((str('Send:') + str('Hello!')))
  wait(1)
  wait_ms(2)
```

### End device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_end_device_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from comx.zigbee import Zigbee

setScreenColor(0x222222)

zigbee = Zigbee(17, 16)
zigbee.set_param_module(3, 0x1617, 20, 1, 0x2345, 6, 1, '')
while True:
  if zigbee.check_payload():
    print((str('Received:') + str((zigbee.recv_payload()))))
  wait_ms(2)
```

## API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_init.svg">

```python
from comx.zigbee import Zigbee
zigbee = Zigbee(17, 16)
```

- Initialize module interface

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_set_module.svg">

```python
zigbee.set_param_module(3, 0x1617, 20, 1, 0x2345, 6, 1, '')
```

- Initialize module parameters:
  - Role:
    - 1:Coordinator
    - 2:Router
    - 3:End Device
  - PAN:0x0001-0xFF00
  - USER ADDRESS: 0x0001-0xFF00
- For more parameter details, please refer to the user manual:
  - [Zigbee_Module_Guide](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/module/Zigbee_CC2630/Zigbee_Module_Guide.pdf)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_set_reboot.svg">

```python
zigbee.reboot_module()
```

- Reboot the module. (Execute reboot to save changes after modifying module configurations.)


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_check_payload.svg">

```python
zigbee.check_payload()
```

- Read the current data cache length.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_recv_payload.svg">

```python
zigbee.recv_payload()
```

- Read data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_send_payload.svg">

```python
zigbee.send_payload('Hello!')
```

- Send data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_set_core_baudrate.svg">

```python
zigbee.core_baudrate(38400)
```

- Set the baud rate for the main control side.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_get_param.svg">

```python
zigbee.get_param_module(index)
```

- Read module configuration parameters:
  - index:
    - 0:ROLE
    - 1:PAN ID
    - 2:CHANNEL
    - 3:MODE
    - 4:USER ADDR
    - 5:BAUDRATE
    - 6:ANTENNA
    - MAC
    - SHORT ADDR
    - PASSWORD


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_zigbee/uiflow_block_com_zigbee_get_version.svg">

```python
zigbee.version_module()
```

- Read module version.

