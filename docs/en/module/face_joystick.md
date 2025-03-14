# Faces Finger

## Example

#> Add a fingerprint user with a specified user ID and access level, then continuously print the user's access level, ID, and status in a loop, and finally remove the user's information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_face_finger_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import face

setScreenColor(0x222222)

faces_finger = face.get(face.FINGER)

faces_finger.addUser(1, 1)
while True:
  print((str('access: ') + str((access))))
  print((str('id: ') + str((user_id))))
  print((str('state: ') + str((faces_finger.state))))
  faces_finger.removeUser(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_add_user.svg">

```python
faces_finger.addUser(1, 1)
```

- Adds a user fingerprint with a specified user ID and access level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_getUnknown.svg">

```python
def faces_finger_unknownCb():
	# global params
  pass
faces_finger.getUnknownCb(faces_finger_unknownCb)
```

- Retrieves information about unregistered fingerprints, typically used to detect if there are any new fingerprints that haven't been recognized.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_get_access.svg">

```python
access
```

- Retrieves the access level of the current fingerprint.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_get_id.svg">

```python
user_id
```

- Retrieves the user ID of the current fingerprint.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_get_state.svg">

```python
faces_finger.state
```

- Retrieves the status information of the current fingerprint.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_read.svg">

```python
def faces_finger_cb(user_id, access):
  # global params
  pass
faces_finger.readFingerCb(callback=faces_finger_cb)
```

- Reads user information with a specific user ID and access level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_removeAll.svg">

```python
faces_finger.removeAllUser()
```

- Removes all stored fingerprint user information. This operation will clear all registered user data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_finger/uiflow_block_faces_finger_remove_user.svg">

```python
faces_finger.removeUser(1)
```

- Removes the fingerprint user information with the specified ID. By entering the user ID, you can delete the corresponding fingerprint user data.