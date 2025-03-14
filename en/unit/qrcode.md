# Unit Unit QRCode

## Example

Automatic scanning of QR code

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
qrcode_0 = unit.get(unit.QRCODE, unit.PORTA)

qrcode_0.init_device_mode(0, 0x21)
qrcode_0.set_trigger_mode(0)
qrcode_0.set_manual_scan(1)
while True:
  if qrcode_0.get_qrcode_data_status():
    print(qrcode_0.get_qrcode_data(False))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_init_mode.svg">

```python
qrcode_0.init_device_mode(0, 0x21)
```

- Create a QRCode Unit object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_clear_current_data_status.svg">

```python
qrcode_0.clear_qrcode_data_status()
```

- Clear the QRCode Unit trigger flag

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_current_data_status.svg">

```python
print(qrcode_0.get_qrcode_data_status())
```

- Get the status of automatic or manual trigger mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_data_format.svg">

```python
print(qrcode_0.get_qrcode_data(False))
```

- Scan a QR code and retrieve the data as a string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_data_length.svg">

```python
print(qrcode_0.get_qrcode_data_length())
```

- Scan a QR code and get the available data length

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_device_info.svg">

```python
print(qrcode_0.get_device_info(0xFE))
```

- Obtain firmware version details and I2C address for this device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_trigger_button.svg">

```python
print(qrcode_0.get_trigger_button_status())
```

- Get the status of the trigger button

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_get_trigger_mode.svg">

```python
print(qrcode_0.get_trigger_mode())
```

- (Duplicate) Get the status of automatic or manual trigger mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_set_i2c_address.svg">

```python
qrcode_0.set_device_i2c_address(0x21)
```

- Allow the user to change the I2C address, which should be between 0x01 and 0x7F

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_set_manual_scan.svg">

```python
qrcode_0.set_manual_scan(1)
```

- Set the scanning mode to manual
  - 1: start to disable
  - 0: stop to enable

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/qrcode/uiflow_block_unit_qrcode_set_trigger_mode.svg">

```python
qrcode_0.set_trigger_mode(0)
```

- Set the trigger mode to automatic or manual (keys)
  - 0: AUTO
  - 1: MANUAL
