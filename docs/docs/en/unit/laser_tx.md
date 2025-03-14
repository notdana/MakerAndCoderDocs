# Unit Laser TX

## Example

<img class="blockly_svg" src="example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
laser_rx_0 = unit.get(unit.LASERRX, unit.PORTB)
laser_tx_0 = unit.get(unit.LASERTX, unit.PORTB)

while True:
  if btnA.wasPressed():
    laser_tx_0.on()
  elif btnB.wasPressed():
    laser_tx_0.off()
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/laser_tx/uiflow_block_lasertx_off.svg">

```python
laser_tx_0.off()
```

- 禁用Unit Laser Tx

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/laser_tx/uiflow_block_lasertx_on.svg">

```python
laser_tx_0.on()
```

- 启动Unit Laser Tx

