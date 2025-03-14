# [Unit Gesture](/en/unit/gesture)

## Example

Unit Gesture reads the gesture

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
gesture_0 = unit.get(unit.GESTURE, unit.PORTA)

gesture_0.begin()
gesture_0.set_gesture_highrate(True)
while True:
  print(gesture_0.get_gesture())
  print(gesture_0.gesture_description((gesture_0.get_gesture())))
  if gesture_0.GestureUp:
    print('up')
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_gesture_begin.svg">

```python
gesture_0.begin()
```

- Initialize Unit

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_gesture_get.svg">

```python
print(gesture_0.get_gesture())
```

- Get gesture

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_gesture_get_desc.svg">

```python
print(gesture_0.gesture_description((gesture_0.get_gesture())))
```

- Get the description (get the value of the gesture), used with the obtained gesture value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_gesture_set_highrate.svg">

```python
gesture_0.set_gesture_highrate(True)
```

- Set high speed (true or false)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gesture/uiflow_block_gesture_status.svg">

```python
print(gesture_0.GestureNone)
```

- Gesture value Returns the value of the potential. It is mainly used for logical operations.
- If set to UP, Unit retrieves the gesture made by the user as up and returns true
