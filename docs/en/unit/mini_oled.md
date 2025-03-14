# [Mini Unit Oled](/en/unit/MiniOLED%20Unit)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x272727)
mini_oled_0 = unit.get(unit.MINI_OLED, unit.PORTA)

i = None

# Describe this function...
def text_scroll():
  global i
  mini_oled_0.fill(0)
  mini_oled_0.text('WELCOME', 8, 4, 1)
  mini_oled_0.text('M5', 30, 18, 1)
  mini_oled_0.text('MINI OLED', 0, 32, 1)
  mini_oled_0.show()
  for count in range(5):
    mini_oled_0.invert(1)
    mini_oled_0.show()
    wait_ms(250)
    mini_oled_0.invert(0)
    mini_oled_0.show()
    wait_ms(250)
  for i in range(11):
    mini_oled_0.scroll(i, i)
    mini_oled_0.show()
    wait_ms(250)

def buttonA_wasPressed():
  global i
  text_scroll()
  pass
btnA.wasPressed(buttonA_wasPressed)

text_scroll()
wait_ms(200)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_display_brightness.svg">

```python
mini_oled_0.contrast(150)
```

- Set the display brightness

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_display_color.svg">

```python
mini_oled_0.invert(1)
```

- Set display color (reversible)
  - 0 :INVERT
  - 1 :NORMAL

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_display_power.svg">

```python
mini_oled_0.power_ctrl(0x00)
```

- Set display switch (NO/OFF)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_display_scroll.svg">

```python
mini_oled_0.scroll(0, 0)
```

- Set screen scrolling (X\Y)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_display_show.svg">

```python
mini_oled_0.show()
```

- Indicates whether the function is enabled

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_fill.svg">

```python
mini_oled_0.fill(1)
```

- Fill color
  - 1: White
  - 0: Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_fill_rect.svg">

```python
mini_oled_0.fill_rect(0, 0, 0, 0, 1)
```

- Fill the specified area color
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_hline.svg">

```python
mini_oled_0.hline(0, 0, 0, 1)
```

- Draw horizontal lines
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_line.svg">

```python
mini_oled_0.line(0, 0, 0, 0, 1)
```

- Draw a straight line between two points
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_pixel.svg">

```python
mini_oled_0.pixel(0, 0, 1)
```

- Draw pixels
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_rect.svg">

```python
mini_oled_0.rect(0, 0, 0, 0, 1)
```

- Draw a square
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_text.svg">

```python
mini_oled_0.text('', 0, 0, 1)
```

- Show text
  - Color(1): White
  - Color(0): Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/mini_oled/uiflow_block_unit_minioled_vline.svg">

```python
mini_oled_0.vline(0, 0, 0, 1)
```

- Draw vertical lines
  - Color(1): White
  - Color(0): Black