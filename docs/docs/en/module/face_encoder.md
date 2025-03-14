# Faces Encoder

## Example

#> Reset the encoder value, set the first LED to red, and continuously print the encoder's rotation direction, button status, and current value in a loop.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_face_encoder_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import face

setScreenColor(0x222222)

faces_encode = face.get(face.ENCODE)

faces_encode.clearValue()
faces_encode.setLed(0, 0xff0000)
while True:
  print((str('direction: ') + str((faces_encode.getDir()))))
  print((str('press status: ') + str((faces_encode.getPress()))))
  print((str('value: ') + str((faces_encode.getValue()))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_clearValue.svg">

```python
faces_encode.clearValue()
```

- Resets the current value of the encoder to zero.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_getDir.svg">

```python
faces_encode.getDir()
```

- Retrieves the rotation direction of the encoder. The returned value indicates the current rotation direction of the encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_getPress.svg">

```python
faces_encode.getPress()
```

- Checks if the encoder button is pressed. Returns a boolean value (True/False) to indicate the button's status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_getValue.svg">

```python
faces_encode.getValue()
```

- Retrieves the current encoder value. The returned value represents the current position of the encoder.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_setLed.svg">

```python
faces_encode.setLed(0, 0xff0000)
```

- Sets the color of the LED at a specific position. You can choose the LED position and color.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_setLed_input.svg">

```python
faces_encode.setLed(0, 0xff0000)
```

- Sets the color of the LED at the specified position. You can choose the color from a palette and apply it to the specified LED position (e.g., position 0).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_encoder/uiflow_block_faces_encode_setLed_rgb.svg">

```python
faces_encode.setLed(0, 0x000000)
```

- Sets the color of the LED at the specified position by manually inputting red, green, and blue (RGB) values to determine the final color of the LED. This allows for more precise control over the LED's color output.