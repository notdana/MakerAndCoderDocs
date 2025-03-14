# Module USB

## Example

#>Initialize the mouse HID HOST, and after connecting the mouse, read the cursor's x, y coordinates and button status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time
setScreenColor(0x222222)

usb = module.get(module.USBHOST)

usb.max3421e_init(sclk=18, mosi=23, miso=19, cs=5, irq=35)
usb.hid_init()
while True:
  usb.hid_poll()
  if usb.mouse_button_status(1):
    print('mouse button left click')
  if usb.mouse_button_status(2):
    print('mouse button right click')
  if usb.mouse_button_status(4):
    print('mouse button center click')
  print((str('X:') + str((usb.mouse_cursor_x))))
  print((str('Y:') + str((usb.mouse_cursor_y))))
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_module_usb_init_max3421.svg">

```python
import module
usb = module.get(module.USBHOST)
usb.max3421e_init(sclk=18, mosi=23, miso=19, cs=5, irq=35)
```

- Initialize the USB Module.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_init.svg">

```python
usb.hid_init()
```

- Initialize Mouse HID Host


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_hid_poll.svg">


```python
usb.hid_poll()
```

- Refresh the status of the input devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_mouse_get_click_status.svg">

```python
usb.mouse_button_status(status):
```

- Get the button status:
  - status:
    - left:1
    - right:2
    - left+right:3
    - center:4
    - left+center:5
    - right+center:6
    - left+right+center:7
- Return:
  - True/False


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_mouse_cutsor.svg">

```python
usb.mouse_cursor_x
usb.mouse_cursor_y
```

- Get the cursor position of the input device


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_read_output_pin_value.svg">

```python
usb.write_output_pin(PIN,0)
```

- Module output IO, control the output voltage level
  - PIN:0-4

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_read_input_pin.svg">

```python
usb.read_input_pin(PIN)
```

- Module input IO, read the input voltage level
  - PIN:0-4

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/usb/uiflow_block_usb_read_output_pin.svg">

```python
usb.read_output_pin(PIN)
```

- Module output IO, read the output voltage level.
  - PIN:0-4

