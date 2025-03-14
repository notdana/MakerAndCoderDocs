# [Unit Glass2](/en/unit/Glass2%20Unit)

## Example

draw the text

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

glass2_0 = unit.get(unit.GLASS2_OLED, unit.PORTA)

font_size = None
from numbers import Number

font_size = 0
glass2_0.fill(0x000000)
for count in range(4):
  font_size = (font_size if isinstance(font_size, Number) else 0) + 1
  if font_size == 1:
    glass2_0.print('M5STACK', 0, 0, 1, 0xffffff)
  elif font_size == 2:
    glass2_0.print('M5STACK', 10, 0, 2, 0xffffff)
  elif font_size == 3:
    glass2_0.print('M5STACK', 25, 0, 3, 0xffffff)
  elif font_size == 4:
    glass2_0.print('M5STACK', 40, 0, 4, 0xffffff)
    font_size = 0
  glass2_0.show()
  wait_ms(500)
glass2_0.fill(0x000000)
glass2_0.show()
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_init.svg">

```python
glass2_0.init_device_address(0x3C)
```

- Set I2C address (0x3C~0x3D)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_display_brightness.svg">

```python
glass2_0.contrast(0)
```

- Set screen brightness

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_display_invert.svg">

```python
glass2_0.invert(1)
```

- Set screen color (normal display or inverted color)
  - 0: NORMAL
  - 1: REVERSE

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_display_power.svg">

```python
glass2_0.power_ctrl(0x00)
```

- Turn screen power on and off (ON/OFF)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_display_scroll.svg">

```python
glass2_0.scroll(0, 0)
```

- Make a new copy of the contents of the more than one running code screen and define the initial location

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_display_show.svg">

```python
glass2_0.show()
```

- Turn on screen display


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_fill.svg">

```python
glass2_0.fill(0xffffff)
```

- Set full-screen color
  - White: White
  - Black: Black

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_fill_rect.svg">

```python
glass2_0.fill_rect(0, 0, 0, 0, 0xffffff)
```

- Draw a square

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_hline.svg">

```python
glass2_0.hline(0, 0, 0, 0xffffff)
```

-- Draw a horizontal line

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_image.svg">

```python
glass2_0.image(0, 0, "/flash/img/m5stack.pbm")
```

- Fill external resource image

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_line.svg">

```python
glass2_0.line(0, 0, 0, 0, 0xffffff)
```

- Draw a line, input coordinates from point to point

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_pixel.svg">

```python
glass2_0.pixel(0, 0, 0xffffff)
```

- Input pixel for display

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_rect.svg">

```python
glass2_0.rect(0, 0, 0, 0, 0xffffff)
```

- Draw a rectangle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_text.svg">

```python
glass2_0.print('M5Stack', 0, 0, 1, 0xffffff)
```

- Draw text

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass2/uiflow_block_unit_glass2_vline.svg">

```python
glass2_0.vline(0, 0, 0, 0xffffff)
```

- Draw a vertical line

