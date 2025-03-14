# CAN

## Example

Use ESP32 internal CAN controller resources to realize CAN bus data sending and receiving, Note: Before using, you need to access [CAN UNIT](https://shop.m5stack.com/products/canbus-unitca-is3050g) for the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from machine import CAN
import time

setScreenColor(0x222222)

frame = None

label0 = M5TextBox(16, 53, "Device State: ", lcd.FONT_Default, 0x00ff7c, rotate=0)
label1 = M5TextBox(126, 53, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label2 = M5TextBox(16, 97, "message: ", lcd.FONT_Default, 0x00ff7c, rotate=0)
label3 = M5TextBox(16, 132, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label4 = M5TextBox(16, 162, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label5 = M5TextBox(16, 192, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)

def buttonA_wasPressed():
  global frame
  can.send([0, 1, 2, 3, 4, 5, 6, 7], 0)
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  global frame
  can.clear_tx_queue()
  can.clear_rx_queue()
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  global frame
  can.restart()
  pass
btnC.wasPressed(buttonC_wasPressed)


can = CAN(0, extframe=True, mode=CAN.NORMAL, baudrate=CAN.BAUDRATE_25K, tx_io=17, rx_io=16, auto_restart=False)
while True:
  label1.setText(str(can.state()))
  if can.any():
    frame = can.recv()
    label3.setText(str(frame[0]))
    label4.setText(str(frame[1]))
    label5.setText(str(frame[3]))
  wait_ms(30)
  wait_ms(2)

```

## API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_init.svg">

```python
from machine import CAN
can = CAN(0, extframe=True, mode=CAN.NORMAL, baudrate=CAN.BAUDRATE_25K, tx_io=17, rx_io=16, auto_restart=False)
```

- Initialize CAN bus, configure frame expansion mode, operating mode (normal mode, loopback mode, etc.) and baud rate setting.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_any.svg">

```python
can.any()
```

- Check for unread data in FIFOs


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_recv.svg">

```python
frame = can.recv()
```

- receive data


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_send.svg">

```python
can.send([0, 1, 2, 3, 4, 5, 6, 7], id)
```

- Sends a piece of data and specifies the ID of the data frame, the ID length is 1 byte, the incoming data type is required to be `list` or `tuple`, and the data length of the data frame is required to be `8 bytes`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_set_filter.svg">

```python
can.setfilter(0, CAN.FILTER_RAW_SINGLE, [])
```

- Setting up filter groups

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_state.svg">

```python
can.state()
```

- Get CAN controller status


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_clear_rx_queue.svg">

```python
can.clear_rx_queue()
```

- Clear the receive queue

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_clear_tx_queue.svg">

```python
can.clear_tx_queue()
```

- Clearing the send queue


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_clearfilter.svg">

```python
can.clearfilter()
```

- Clear Filter Groups


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_restart.svg">

```python
can.restart()
```

- Reboot CAN bus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/can/uiflow_block_can_deinit.svg">

```python
can.deinit()
```

- Stop CAN bus

