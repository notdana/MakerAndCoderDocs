# [Unit OLED](/en/unit/oled)

## Example

Draw the M5Stack graph

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
oled_1 = unit.get(unit.OLED, unit.PORTA)

while True:
  oled_1.fill(0x000000)
  oled_1.show()
  oled_1.text('Unit OLED Example', 0, 0, 0xffffff)
  oled_1.show()
  wait(5)
  oled_1.fill(0x000000)
  oled_1.show()
  oled_1.image(25, 0, "/flash/img/m5stack.pbm")
  oled_1.show()
  wait(5)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_fill.svg">

```python
oled_0.fill(0xffffff)
```

- Set screen color fill
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_fill_rect.svg">

```python
oled_0.fill_rect(0, 0, 0, 0, 0xffffff)
```

- Fill a specified area with color
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_hline.svg">

```python
oled_0.hline(0, 0, 0, 0xffffff)
```

- Draw a horizontal line
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_image.svg">

```python
oled_0.image(0, 0, "/flash/img/m5stack.pbm")
```

- Fill with an image

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_invert.svg">

```python
oled_0.invert(1)
```

- Set screen rotation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_line.svg">

```python
oled_0.line(0, 0, 0, 0, 0xffffff)
```

- Draw a horizontal line
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_pixel.svg">

```python
oled_0.pixel(0, 0, 0xffffff)
```

- Draw a pixel
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_poweroff.svg">

```python
oled_0.poweroff()
```

- Turn off power

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_poweron.svg">

```python
oled_0.poweron()
```

- Turn on power

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_rect.svg">

```python
oled_0.rect(0, 0, 0, 0, 0xffffff)
```

- Draw a rectangle
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_scroll.svg">

```python
oled_0.scroll(0, 0)
```

- Scroll the screen

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_show.svg">

```python
oled_0.show()
```

- Activate Unit 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_text.svg">

```python
oled_0.text('', 0, 0, 0xffffff)
```

- Draw text
  - White
  - Black 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/oled/uiflow_block_oled_vline.svg">

```python
oled_0.vline(0, 0, 0, 0xffffff)
```

- Draw a vertical line
  - White
  - Black 
