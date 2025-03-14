# Faces RFID

## Example

#> Detect if an RFID card is nearby, read the card's UID and a string from a specified address, and write the string "rfid" to address 1 of the card.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_rfid/uiflow_block_face_rfid_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import face

setScreenColor(0x222222)

faces_rfid = face.get(face.RFID)

while True:
  print((str('status: ') + str((faces_rfid.isCardOn()))))
  print((str('read card: ') + str((faces_rfid.readBlockStr((faces_rfid.isCardOn()))))))
  print((str('uid: ') + str((faces_rfid.readUid()))))
  faces_rfid.writeBlock(1, 'rfid')
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_rfid/uiflow_block_faces_rfid_cardOn.svg">

```python
faces_rfid.isCardOn()
```

- Checks if an RFID card is near the reader. If a card is detected, the system will trigger the corresponding action.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_rfid/uiflow_block_faces_rfid_readStr.svg">

```python
faces_rfid.readBlockStr(faces_rfid.isCardOn())
```

- Reads the string information stored at a specific address on the RFID card. The address is a location within the RFID card's memory.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_rfid/uiflow_block_faces_rfid_uid.svg">

```python
faces_rfid.readUid()
```

- Retrieves the UID of the currently scanned RFID card. This UID is unique and can be used to uniquely identify a card.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/face_rfid/uiflow_block_faces_write_block.svg">

```python
faces_rfid.writeBlock(1, 'rfid')
```

- Writes the specified string data to a specific storage address on the RFID card. The data written can be any text information.