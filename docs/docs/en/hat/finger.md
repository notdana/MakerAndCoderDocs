# Hat Finger

## Example

> Prints fingerprint ID, access level, and recognition status to the serial console.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import hat

setScreenColor(0x111111)

hat_Finger_0 = hat.get(hat.FINGER)

hat_Finger_0.addUser(1, 1)
while True:
  print(hat_Finger_0.state)
  print(user_id)
  print(access)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_add_user.svg">

```python
hat_Finger_0.addUser(1, 1)
```

- Adds a fingerprint user ID and assigns an access level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_getUnknown.svg">

```python
hat_Finger_0.readFingerCb(callback=hat_Finger_0_cb)
```

- Retrieves the status of an unknown user.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_get_access.svg">

```python
access
```

- Gets the access level information of the fingerprint user.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_get_id.svg">

```python
user_id
```

- Retrieves the ID of the fingerprint user.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_get_state.svg">

```python
hat_Finger_0.state
```

- Gets the status of the fingerprint recognition module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_read.svg">

```python
hat_Finger_0.state
```

- Reads information of a user with a specific ID and access level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_removeAll.svg">

```python
hat_Finger_0.removeAllUser()
```

- Deletes all stored user data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/finger/uiflow_block_hat_finger_remove_user.svg">

```python
hat_Finger_0.removeUser(1)
```

- Deletes the fingerprint data of a specified user ID.