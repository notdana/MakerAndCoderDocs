# Faces Keyboard

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import face

setScreenColor(0x222222)

faces_keyboard = face.get(face.KEYBOARD)

def buttonA_wasPressed():
  # global params
  faces_keyboard.clearStr()
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  # global params
  faces_keyboard.deleteStrLast()
  pass
btnB.wasPressed(buttonB_wasPressed)


while True:
  if faces_keyboard.isNewKeyPress():
    print((str('Button value:') + str((faces_keyboard.readKey()))))
    print((str('Input string:') + str((faces_keyboard.readStr()))))
  wait_ms(2)
```

## API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_isNewKeyPress.svg">

```python
faces_keyboard.isNewKeyPress()
```

- Detects if a new key is pressed:
  - True:New button pressed
  - False:No new buttons pressed

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_readKey.svg">

```python
faces_keyboard.readKey()
```

- Read the input key value


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_readStr.svg">

```python
faces_keyboard.readStr()
```

- Reads the input string. Successive inputs will be accumulated.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_deleteStrLast.svg">

```python
faces_keyboard.deleteStrLast()
```

- Delete the last character entered


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_keyboard/uiflow_block_faces_keyboard_clearStr.svg">

```python
faces_keyboard.clearStr()
```

- Clear the entered string


