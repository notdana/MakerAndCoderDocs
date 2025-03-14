# Atomic Stepmotor Base

## Example

> This program controls the PWM signal and direction switching. Single and double presses of button A toggle the run state and direction flag. When the run flag `run_flag` is 1, the PWM signal resumes and drives the device. Depending on whether the direction flag `dir_flag` is 0 or 1, pin 23’s output is set to high or low to change the direction. The ADC read value monitors the input signal, and the RGB LED color indicates the running state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_atomic_base_stepmotor_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from easyIO import *
import machine

dir_flag = None
run_flag = None
adc_val = None

def buttonA_wasDoublePress():
  global dir_flag, run_flag, adc_val, adc0, PWM0
  if dir_flag == 0:
    dir_flag = 1
  else:
    dir_flag = 0
  pass
btnA.wasDoublePress(buttonA_wasDoublePress)

def buttonA_wasPressed():
  global dir_flag, run_flag, adc_val, adc0, PWM0
  if run_flag == 0:
    rgb.setColorAll(0x33ff33)
    run_flag = 1
  else:
    rgb.setColorAll(0x000000)
    run_flag = 0
  pass
btnA.wasPressed(buttonA_wasPressed)

digitalWrite(21, 1)
digitalWrite(22, 0)
dir_flag = 0
run_flag = 0
adc0 = machine.ADC(33)
adc0.width(machine.ADC.WIDTH_12BIT)
adc0.atten(machine.ADC.ATTN_11DB)
adc_val = 0
rgb.setColorAll(0x000000)
PWM0 = machine.PWM(19, freq=12000, duty=0, timer=0)
PWM0.pause()
PWM0.duty(50)
while True:
  adc_val = adc0.read()
  if run_flag == 1:
    PWM0.resume()
  else:
    PWM0.pause()
  if dir_flag == 1:
    digitalWrite(23, 1)
  else:
    digitalWrite(23, 0)
  print(adc_val)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_init.svg">

```python
stepmotor = Stepmotor('Full')
```

- Initializes the stepper motor, setting the stepping mode to full step, which affects the motor’s stepping style and precision.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_disbale.svg">

```python
stepmotor.disable()
```

- Disables the stepper motor, stopping its operation so it will no longer receive movement commands.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_enable.svg">

```python
stepmotor.enable()
```

- Enables the stepper motor, allowing it to begin executing commands and responding to control signals.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_get_status.svg">

```python
stepmotor.get_status()
```

- Gets the status of the stepper motor, typically used to check whether the motor is enabled or operating normally.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_get_voltage.svg">

```python
stepmotor.get_voltage()
```

- Retrieves the voltage of the stepper motor, potentially for monitoring power supply conditions to ensure the motor operates within the correct voltage range.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_move_circles.svg">

```python
stepmotor.move_circles(0, 0)
```

- Sets the motor to rotate a specified number of circles in a clockwise direction, used to control the motor's rotation angle.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_move_steps.svg">

```python
stepmotor.move_steps(0, 0)
```

- Sets the motor to move a specified number of steps in a clockwise direction, allowing precise control over the motor’s rotation angle.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/stepmotor/uiflow_block_base_stepmotor_reset.svg">

```python
stepmotor.reset()
```

- Resets the stepper motor or a connected device to its initial state.