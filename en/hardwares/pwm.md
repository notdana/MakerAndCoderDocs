# PWM

## Example

Initialize the direction of the pin, and print the value of the pin on the screen.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_demo.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import machine
import time


screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

i = None

label0 = M5Label('label0', x=137, y=88, color=0x000, font=FONT_MONT_14, parent=None)

PWM0 = machine.PWM(26, freq=50, duty=3, timer=0)
while True:
  for i in range(13):
    PWM0.duty(i)
    wait_ms(1000)
    label0.set_text(str(i))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm.svg"> 

```python
machine.PWM(26, freq=10000, duty=50, timer=0)
```

- Set the pin, frequency, duty cycle, and timer selection for generating PWM signals.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_freq.svg"> 

```python
PWM0.freq(1)
```

- Set the PWM frequency.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_duty.svg"> 

```python
PWM0.duty(0)
```

- Set the PWM duty cycle.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_pause.svg"> 

```python
PWM0.pause()
```

- Pause PWM signal generation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_resume.svg"> 

```python
PWM0.resume()
```

- Resume PWM signal generation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/pwm/uiflow_block_pwm_hold_us.svg"> 

```python
PWM0.hold_us(0)
```

- Hold the PWM signal for a few microseconds.