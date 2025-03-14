# Hat Heart Rate

## Example

> Retrieves heart rate and blood oxygen values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heart_rate_demo.png">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import hat

setScreenColor(0x111111)

hat_heartrate_0 = hat.get(hat.HEART_RATE)

hat_heartrate_0.setMode(0x03)
while True:
  print(hat_heartrate_0.getHeartRate())
  print(hat_heartrate_0.getSpO2())
  wait(0.4)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_get_heartrate.svg">

```python
hat_heartrate_0.getHeartRate()
```

- Retrieves heart rate data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_get_ir.svg">

```python
hat_heartrate_0.getIr()
```

- Gets the infrared raw ADC value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_get_red.svg">

```python
hat_heartrate_0.getRed()
```

- Gets the red light raw ADC value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_get_spo2.svg">

```python
hat_heartrate_0.getSpO2()
```

- Retrieves blood oxygen saturation (SpO2) data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_set_led_current.svg">

```python
hat_heartrate_0.setLedCurrent(0x00, 0x00)
```

- Sets the current values for the red and infrared LEDs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hat/heart_rate/uiflow_block_hat_heartrate_set_mode.svg">

```python
hat_heartrate_0.setMode(0x02)
```

- Sets the mode for heart rate or other measurements.