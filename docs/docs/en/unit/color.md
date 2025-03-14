# [Unit Color](/en/unit/color)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
color_0 = unit.get(unit.COLOR, unit.PORTA)

while True:
  print((str('R:') + str(str((color_0.red)))))
  print((str('G:') + str(str((color_0.green)))))
  print((str('B:') + str(str((color_0.blue)))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_getD.svg">

```python
print(color_0.rawData)
```

- get rawData

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_getB.svg">

```python
print(color_0.blue)
```

- get Blue value


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_getG.svg">

```python
print(color_0.green)
```

- get Green value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_getR.svg">

```python
print(color_0.red)
```

- get Red value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_set_gain.svg">

```python
color_0.setGains(0x00)
```

- set gain value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/color/uiflow_block_color_set_integration_time.svg">

```python
color_0.setIntegrationTime(0xFF)
```

- set integration value 

