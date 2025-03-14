# POWER

## Example

Wait for 5 seconds to power on, then power off after one second.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_demo.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import time
screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
power.restart_after_seconds(0)
wait(1)
power.powerOff()
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_charge_state.svg"> 

```python
str(power.getChargeState())
```

- Returns the charging state and outputs it as a string.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_bat_voltage.svg"> 

```python
str(power.getChargeState())
```
 
- Converts the returned battery voltage value to a string and outputs it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_bat_voltage_percent.svg"> 

```python
str(power.getBatPercent())
```

- Converts the returned battery percentage to a string and outputs it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_bat_current.svg"> 

```python
str(power.getBatCurrent())
```

- Converts the returned battery current value to a string and outputs it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_bat_current.svg"> 

```python
str(power.getBatCurrent())
```

- Converts the returned battery output current value to a string and outputs it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_vbus_voltage.svg"> 

```python
str(power.getVBusVoltage())
```

- Converts the returned VBus voltage value to a string and outputs it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_get_temperature.svg"> 

```python
str(power.getPmuInTemp())
```

- Converts the returned PMU internal temperature value to a string and outputs it.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_power_off.svg"> 

```python
power.powerOff()
```

- Powers off.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_set_charge_current.svg"> 

```python
power.setChargeCurrent(power.CURRENT_100MA)
```

- Sets the charging current.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_set_screen_brightness.svg"> 

```python
screen.set_screen_brightness(30)
```

- Sets the screen brightness.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_set_led.svg"> 

```python
power.setPowerLED(True)
```

- Sets the power indicator LED on or off.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_set_bus_mode.svg"> 

```python
power.setBusPowerMode(1)
```

- Sets whether the Mbus bus power is output.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_set_restart.svg"> 

```python
power.restart_after_seconds(0)
```

- Sets the number of seconds until restart.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/power/uiflow_block_power_restart_on.svg"> 

```python
power.restart_on(minutes=0, hours=0, date=1, weekday=0)
```

- Sets a specific time to restart.