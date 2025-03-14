# Atomic CAN Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.CAN import CAN
import time
frame = None
atom_can = CAN()

def buttonA_wasPressed():
  global frame
  atom_can.send([0, 1, 2, 3, 4, 5, 6, 7], 0)
  pass
btnA.wasPressed(buttonA_wasPressed)

atom_can.can_init(0, extframe=True, mode=atom_can.NORMAL, baudrate=atom_can.BAUDRATE_250K, tx_io=22, rx_io=19, auto_restart=False)
while True:
  print((str('status:') + str(atom_can.state())))
  if atom_can.any():
    frame = atom_can.recv()
    print((str('data:') + str(frame)))
  wait_ms(30)
  wait_ms(2)
```
 Base

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_init.svg">

```python
from base.CAN import CAN
atom_can = CAN()
atom_can.can_init(0, extframe=True, mode=atom_can.NORMAL, baudrate=atom_can.BAUDRATE_250K, tx_io=22, rx_io=19, auto_restart=False)
```

- Initialize the CAN bus, configure whether it is in extended frame mode, set the operating mode (normal mode, loopback mode, etc.), and set the baud rate.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_any.svg">

```python
atom_can.any()
```

- Check if there is unread data in the FIFO.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_recv.svg">

```python
frame = atom_can.recv()
```

- Receive data.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_send.svg">

```python
atom_can.send([0, 1, 2, 3, 4, 5, 6, 7], id)
```

- Send a data frame with the specified ID. The ID length is `1 byte`, and the data must be of type `list` or `tuple`, with a data frame length of `8 bytes`.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_set_filter.svg">

```python
atom_can.setfilter(0, CAN.FILTER_RAW_SINGLE, [])
```

- Set a filter group.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_state.svg">

```python
atom_can.state()
```

- Get the CAN controller status.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_clear_rx_queue.svg">

```python
atom_can.clear_rx_queue()
```

- Clear the receive queue.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_clear_tx_queue.svg">

```python
atom_can.clear_tx_queue()
```

- Clear the transmit queue.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_clearfilter.svg">

```python
atom_can.clearfilter()
```

- Clear the filter group.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_restart.svg">

```python
atom_can.restart()
```

- Restart the CAN bus.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/can/uiflow_block_atom_can_deinit.svg">

```python
atom_can.deinit()
```

- Stop the CAN bus.
