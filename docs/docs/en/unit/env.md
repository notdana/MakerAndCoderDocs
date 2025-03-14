# [Unit ENV/ENV-II/ENV-III/ENV-IV](/en/unit/env)

## Example

Get temperature, humidity, and atmospheric pressure data collected by ENV

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import * 
from uiflow import *
import unit

setScreenColor(0x222222)
env_0 = unit.get(unit.ENV, unit.PORTA)

while True:
  print(env_0.temperature)
  print(env_0.humidity)
  print(env_0.pressure)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/uiflow_block_dht12_get_temperature.svg">

```python
print(env_0.temperature)
```

- This method allows you to read the temperature value collected by ENV and return a floating-point value. The unit of measurement is °C.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/uiflow_block_dht12_get_humidity.svg">

```python
print(env_0.humidity)
```

- This method allows you to read the relative humidity value taken by ENV and return a floating-point value. The unit of measurement is %RH.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/uiflow_block_dht12_pressure.svg">

```python
print(env_0.pressure)
```

- This method allows you to read the atmospheres collected by ENV and return a floating-point value. The unit of measurement is Pa.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/enviv/uiflow_block_unit_env4_get_mode.svg">

```python
env4_0.set_mode(0xFD)
```

- Set the device running mode. This function only applies to ENV IV

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/env/enviv/uiflow_block_unit_env4_get_mode.svg">

```python
print(env4_0.get_mode)
```

- Obtain the current device running mode. This function only applies to ENV IV
  - NOHEAT_HIGHPRECISION: No heating, maintain high-precision measurement or control
  - NOHEAT_MEDPRECISION: No heating, medium precision
  - NOHEAT_LOWPRECISION: No heating, lowest precision
  - HIGHHEAT_1S: High heating mode, heating cycle of 1 second
  - HIGHHEAT_100MS: High heating mode, heating cycle of 100 milliseconds
  - MEDHEAT_1S: Medium heating mode, heating cycle of 1 second
  - MEDHEAT_100MS: Medium heating mode, heating cycle of 100 milliseconds
  - LOWHEAT_1S: Low heating mode, heating cycle of 1 second
  - LOWHEAT_100MS: Low heating mode, heating cycle of 100 milliseconds