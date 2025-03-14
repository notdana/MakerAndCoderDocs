# Unit CAN

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x5c0000)
can_0 = unit.get(unit.CAN, unit.PORTC)

def buttonB_wasPressed():
  # global params
  can_0.send([10, 20, 30], 0X710)
  pass
btnB.wasPressed(buttonB_wasPressed)

can_0.can_init(0, extframe=True, mode=can_0.NORMAL, baudrate=can_0.BAUDRATE_250K, tx_io=17, rx_io=16, auto_restart=False)
label3.setText(str(can_0.state()))
while True:
  if can_0.any():
    print((str('message:') + str(can_0.recv())))
    print((str('ID:') + str(can_0.remote_id())))
  wait_ms(25)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_deinit.svg">

```python
can_0.deinit()
```

- Close the CAN bus

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_init.svg">

```python
can_0.can_init(0, extframe=True, mode=can_0.NORMAL, baudrate=can_0.BAUDRATE_250K, tx_io=17, rx_io=16, auto_restart=False)
```

- Construct a CAN object on a given bus
  - mode: NORMAL, NO_ACKNOWLEDGE, LISTEN_ONLY
  - tx: pin used for transmitting data
  - rx: pin used for receiving data
  - baudrate: baud rate
  - extframe: extended frame enabled

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_any.svg">

```python
print(can_0.any())
```

- Check if there is a message waiting on the FIFO Queue

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_clearfilter.svg">

```python
can_0.clear_filter()
```

- Clear data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_clear_rx_queue.svg">

```python
can_0.clear_rx_queue()
```

- Reset all pending messages in the Receive Queue (RX Queue)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_clear_tx_queue.svg">

```python
can_0.clear_tx_queue()
```

- Reset all pending messages in the Transmit Queue (TX Queue)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_get_remoteid.svg">

```python
print(can_0.remote_id())
```

- Get the Remote ID

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_recv.svg">

```python
print(can_0.recv())
```

- Retrieve received data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_restart.svg">

```python
can_0.restart()
```

- Force a software reset of the CAN controller

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_send.svg">

```python
can_0.send('uiflow2', 0)
```

- Send data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_set_filter.svg">

```python
can_0.set_filter(0, can_0.FILTER_RAW_SINGLE, 'uiflow2')
```

- Send data
  - bank:number
  - mode:filter raw single/filter raw dual/filter address
  - Message:string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/can/uiflow_block_unit_can_state.svg">

```python
print(can_0.state())
```

- Return the status of the controller
