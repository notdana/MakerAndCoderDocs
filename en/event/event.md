# Event

## Loop

### Example

- Loop print Hello M5

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_loop_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *

setScreenColor(0x222222)

while True:
  print('Hello M5')
  wait_ms(2)
```


### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_loop.svg"> 

```python
while True:
  wait_ms(2)
```

- Infinite loop execution of the program contained in the Loop

## Button

### Example

- Getting the state of a key by callback or polling

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *

setScreenColor(0x222222)

def multiBtnCb_AB():
  # global params
  print('Button A + B Pressed')
  pass
btn.multiBtnCb(btnA,btnB,multiBtnCb_AB)

def buttonA_wasPressed():
  # global params
  print('Button A Pressed')
  pass
btnA.wasPressed(buttonA_wasPressed)

while True:
  if btnB.wasPressed():
    print('Button B wasPressed')
  if btnC.isPressed():
    print('Button C Pressed')
  wait_ms(2)
```

### API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_init.svg"> 

```python
btn = btn.attach([pin])
```

- Initialize the keys and specify the input pins.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_callback.svg">

```python
def buttonA_wasPressed():
  # global params
  print('Button A Pressed')
  pass
btnA.wasPressed(buttonA_wasPressed)
```

- Bind key event callback function, optional event.
  - wasPressed
  - wasReleased
  - LongPress
  - wasDoublePress

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_callback_multi.svg"> 

```python
def multiBtnCb_AB():
  # global params
  print('Button A + B Pressed')
  pass
btn.multiBtnCb(btnA,btnB,multiBtnCb_AB)
```
- Bind multi-key event callback function, only support two-key combination, triggered when pressing keys at the same time.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_read.svg"> 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_button_read_status.svg"> 

```python
if btnB.wasPressed():
  print('Button B wasPressed')
if btnC.isPressed():
  print('Button C Pressed')
```

- Read current key state, return True/False according to event configuration, optional events.
  - wasPressed
  - wasReleased
  - LongPress
  - wasDoublePress
  - Pressed
  - Released

## Software Timer

### Example

- Configure the software timer to print in 100ms cycles.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_software_timer_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *

setScreenColor(0x222222)

@timerSch.event('timer1')
def ttimer1():
  # global params
  print('This is a software timer!')
  pass


timerSch.setTimer('timer1', 100, 0x00)
timerSch.run('timer1', 100, 0x00)
```

### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_software_timer_callback.svg"> 

```python
@timerSch.event('timer1')
def ttimer1():
  # global params
  pass
```

- Setting the Software Timer Callback Function

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_software_timer_set.svg"> 

```python
timerSch.setTimer('timer1', 100, 0x00)
```

- Sets the software timer period. the timer mode supports the following configurations:
  - PERIODIC 0x00: Cycle execution
  - ONE_SHOT 0x01: Single execution

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_software_timer_start.svg"> 

```python
timerSch.run('timer1', 100, 0x00)
```

- Enable the software timer to configure the period at the same time. the timer mode supports the following configurations:
  - PERIODIC 0x00: Cycle execution
  - ONE_SHOT 0x01: Single execution


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_software_timer_stop.svg"> 

```python
timerSch.stop('timer1')
```

- Stopping the software timer

## Hardware Timer

### Example

- Configure the hardware timer to print in 100ms cycles.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_hardware_timer_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *

setScreenColor(0x222222)

def callback_timer3(_arg):
  # global params
  print('This is a hardware timer!')
  pass


timerSch.timer.init(period=100, mode=timerSch.timer.PERIODIC, callback=callback_timer3)
```

### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_hardware_timer_set.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/event/uiflow_block_hardware_timer_callback.svg"> 


```python
def callback_timer3(_arg):
  pass

timerSch.timer.init(period=100, mode=timerSch.timer.PERIODIC, callback=callback_timer3)
```

- Configure the timer period, timer mode, and callback function. The timer mode supports the following configurations:
  - PERIODIC: Cycle execution
  - ONE_SHOT: Single execution


