# Atomic QRCode Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode/uiflow_block_base_qrcode_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.QRCode import QRCode

scan_data = None

qr = QRCode()
while True:
  if btnA.isPressed():
    qr.trigger(0)
  else:
    qr.trigger(1)
  if qr.status():
    scan_data = qr.read()
    if scan_data != None:
      print(scan_data)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode/uiflow_block_base_qrcode_init.svg">

```python
from base.QRCode import QRCode
qr = QRCode()
```

- Initialize Atomic QRCode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode/uiflow_block_base_qrcode_trigger.svg">

```python
qr.trigger(control)
```

- QRCode scan control:
  - ON: 0
  - OFF: 1


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode/uiflow_block_base_qrcode_status.svg">

```python
qr.status()
```

- QRCode scan status:
  - True: Scan successful
  - False: No content scanned

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode/uiflow_block_base_qrcode_read.svg">

```python
qr.read()
```

- Read the scanned result as a string.

