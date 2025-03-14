# Hat Vibrator

## Example

> Increases vibration intensity every second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/vibrator/uiflow_block_hat_vibration_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_vibrator_0 = hat.get(hat.VIBRATOR)

while True:
  hat_vibrator_0.set_duty(10)
  wait(1)
  hat_vibrator_0.set_duty(30)
  wait(1)
  hat_vibrator_0.set_duty(50)
  wait(1)
  hat_vibrator_0.set_duty(70)
  wait(1)
  hat_vibrator_0.set_duty(100)
  wait(1)
  hat_vibrator_0.turn_off()
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/vibrator/uiflow_block_hat_vibrator_set_duty.svg">

```python
hat_vibrator_0.set_duty(50)
```

- Sets the duty cycle of the vibrator (e.g., 50%), controlling the proportion of time the vibrator is active during each cycle.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/vibrator/uiflow_block_hat_vibrator_set_freq.svg">

```python
hat_vibrator_0.set_freq(10)
```

- Sets the vibration frequency (e.g., 10 Hz), controlling how many times per second the vibrator operates.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/vibrator/uiflow_block_hat_vibrator_turn_off.svg">

```python
hat_vibrator_0.turn_off()
```

- Turns off the vibrator, stopping its operation.