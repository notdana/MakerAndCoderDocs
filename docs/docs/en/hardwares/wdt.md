# Watch Dog Timer

## Example

Set the Watch Dog Timer to reset the device when the program abnormally fails to perform the feed operation at the expected time.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/wdt/uiflow_block_wdt_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *
from machine import WDT
import time


setScreenColor(0x222222)

wdt = WDT(timeout=2000)
while True:
  wait(3000)
  wdt.feed()
  wait_ms(2)
```

#### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/wdt/uiflow_block_wdt_init.svg"> 

```python
wdt = WDT(timeout=2000)
```

- Initialize Watch Dog Timer and set the timeout period

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/wdt/uiflow_block_wdt_feed.svg"> 


```python
wdt.feed()
```

- Repeat the feed operation within the timeout period to refresh, and reset the device if the timeout period is too long for the feed.

