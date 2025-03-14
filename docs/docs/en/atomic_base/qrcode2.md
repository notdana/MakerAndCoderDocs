# QR-Code2 Base

## Example

Upon clicking ButtonA, turn on the QR-Code2 LED light, trigger the scan, and output the scanned data to the console if successful.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.QRCode2 import QRCode2
import time

data = None

qrcode2 = QRCode2(1)

def qrcode2_event_cb(qrdata):
  global data
  data = qrdata
  print(data.decode())
  pass

qrcode2.set_event_cb(qrcode2_event_cb)

def buttonA_wasPressed():
  global data
  qrcode2.set_trigger_key()
  pass
btnA.wasPressed(buttonA_wasPressed)

print(qrcode2.get_firmware_version())
print(qrcode2.get_hardware_model())
qrcode2.set_light_brightness(75)
qrcode2.set_trigger_mode(0)

while True:
  qrcode2.event_poll_loop()
  wait_ms(100)
  wait_ms(2)
```

## Functional Description

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_init.svg">

```python
qrcode2 = QRCode2(1)
```

- Get the current baud rate (baud rate) and return an int type data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_get_baudrate.svg">

```python
print(qrcode2.get_baudrate())
```

- Get the current baud rate (baud rate) and return an int type data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_get_data.svg">

```python
print(qrcode2.get_data(False))
```

- Get the currently stored QR code data. The parameter False is used to indicate whether to process the returned data. If the QR code has been successfully read, it will return the data from the QR code.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_get_data_length.svg">

```python
print(qrcode2.get_data_length())
```

- Get the length of the currently stored QR code data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_get_firmware_version.svg">

```python
print(qrcode2.get_firmware_version())
```

- Get the firmware version model.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_get_hardware_model.svg">

```python
print(qrcode2.get_hardware_model())
```

- Get the hardware model.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_baudrate.svg">

```python
qrcode2.set_baudrate(115200)
```

- Set the baud rate to 115200. Configure the serial communication speed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_light_brightness.svg">

```python
qrcode2.set_light_brightness(57)
```

- Set the brightness of the LED assist light to 57% to enable successful scanning of QR codes even in low-light conditions.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_trigger_cmd.svg">

```python
qrcode2.set_trigger_cmd(0x01)
```

- Set the trigger mode. Control the behavior of the QR code scanner, such as continuous scanning or single scanning.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_trigger_key.svg">

```python
qrcode2.set_trigger_key()
```

- Set or trigger the scanning action.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_trigger_mode.svg">

```python
qrcode2.set_trigger_mode(5)
```

- Set the trigger mode of the QR code scanning device. AUTO: automatic triggering; MANUAL: manual triggering.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_set_callback.svg">

```python
data = None

def qrcode2_event_cb(qrdata):
  global data
  data = qrdata
  pass
```

- Callback function, triggered upon successful scanning, and assigns the scanned result to the variable date. (Note: Assuming you meant data rather than date for the variable name.)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/qrcode2/uiflow_block_atom_qrcode2_callback_in_loop.svg">

```python
while True:
  qrcode2.event_poll_loop()
  wait_ms(100)
  wait_ms(2)
```

- Poll the QRCode2 module to check if a new QR code has been scanned.
