# [Unit Finger](/en/unit/finger)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
finger_0 = unit.get(unit.FINGER, unit.PORTE)

label1 = M5TextBox(23, 69, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)
title0 = M5Title(title="FINGERPRINT", x=3, fgcolor=0xFFFFFF, bgcolor=0x0000FF)

def finger_0_cb(user_id, access):
  # global params
  if (access) == 1 and (user_id) == 1:
    rgb.setColorAll(0x33ff33)
    wait(1)
    rgb.setColorAll(0x000000)
  pass
finger_0.readFingerCb(callback=finger_0_cb)

def buttonA_wasPressed():
  # global params
  finger_0.removeAllUser()
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  finger_0.addUser(1, 1)
  pass
btnB.wasPressed(buttonB_wasPressed)

while True:
  label1.setText(str(finger_0.state))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_uart_init.svg">

```python
finger_0.uart_port_id(1)
```

- Set the core component ID

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_add_user.svg">

```python
finger_0.addUser(1, 1)
```

- Add ID and access rights

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_getUnknown.svg">

```python
def finger_0_unknownCb():
  # global params
  pass
finger_0.getUnknownCb(finger_0_unknownCb)
```

- Unknown id and permission Perform the following operations(Callback function)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_get_access.svg">

```python
print(access)
```

- Return access rights

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_get_id.svg">

```python
print(user_id)
```

- Return ID

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_get_state.svg">

```python
print(finger_0.state)
```

- Read the sensor status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_read.svg">

```python
def finger_0_cb(user_id, access):
  # global params
  pass
finger_0.readFingerCb(callback=finger_0_cb)
```

- Add ID and access permission(Callback function)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_removeAll.svg">

```python
finger_0.removeAllUser()
```

- Remove all fingerprint information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/finger/uiflow_block_finger_remove_user.svg">

```python
移出指纹ID
```

- Remove the fingerprint ID

