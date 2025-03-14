# [Unit RFID](/en/unit/rfid)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/rfid/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
rfid_0 = unit.get(unit.RFID, unit.PORTA)

while True:
  print(rfid_0.isCardOn())
  if rfid_0.isCardOn():
    print(rfid_0.readUid())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/rfid/uiflow_block_rfid_cardOn.svg">

```python
print(rfid_0.isCardOn())
```

- RFID card near return 1

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/rfid/uiflow_block_rfid_readStr.svg">

```python
print(rfid_0.readBlockStr(1))
```

- Read data from an address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/rfid/uiflow_block_rfid_uid.svg">

```python
print(rfid_0.readUid())
```

- Returns the UID of the RFID card

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/rfid/uiflow_block_write_block.svg">

```python
rfid_0.writeBlock(1,'M5Stack')
```

- Writes data to an address