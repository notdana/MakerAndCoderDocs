# PIN

## Example

Set the pin to output a high level for 1 second and a low level for 1 second


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_demo1.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import machine
import time

while True:
  pin0.on()
  wait(1)
  pin0.off()
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_pinout.svg"> 

```python
machine.Pin(0, mode=machine.Pin.IN, pull=machine.Pin.PULL_UP)
```

- Set the direction of the pin.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_on.svg"> 

```python
pin0.on()
```
 
- Set the pin to output high level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_off.svg"> 

```python
pin0.off()
```

- Set the pin to output low level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_set_value.svg"> 

```python
pin0.value(0)
```

- Set the value of the pin.
  - "0": Low level
  - "1": High level

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pin/uiflow_block_pin_get_value.svg"> 

```python
str(pin0.value())
```

- Get the value read from the pin.