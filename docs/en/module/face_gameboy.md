# Faces Gameboy

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_gameboy/uiflow_block_faces_gameboy_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import face

setScreenColor(0x222222)

faces_boy = face.get(face.GAMEBOY)

while True:
  if faces_boy.getStatus(0):
    print('up')
  if faces_boy.getStatus(1):
    print('down')
  if faces_boy.getStatus(2):
    print('left')
  if faces_boy.getStatus(3):
    print('right')
  if faces_boy.getStatus(4):
    print('Button A')
  if faces_boy.getStatus(5):
    print('Button B')
  if faces_boy.getStatus(6):
    print('Button Select')
  if faces_boy.getStatus(7):
    print('Button Start')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_gameboy/uiflow_block_faces_gameboy_getPressed.svg">

```python
faces_boy.getPressed(key)
```

```python
faces_boy.getReleased(key)
```

- Detecting gameboy key click, release events.
  - key:
    - 0:up
    - 1:down
    - 2:left
    - 3:right
    - 4:BtnA
    - 5:BtnB
    - 6:Btn Select
    - 7:Btn Start


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_gameboy/uiflow_block_faces_gameboy_getStatus.svg">

```python
faces_boy.getStatus(key)
```

- Detecting gameboy keyboard key press status
  - key:
    - 0:up
    - 1:down
    - 2:left
    - 3:right
    - 4:BtnA
    - 5:BtnB
    - 6:Btn Select
    - 7:Btn Start


