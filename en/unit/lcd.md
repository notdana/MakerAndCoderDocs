# [Unit LCD](/en/unit/lcd)

## Example

Draw basic graphics and text

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_example.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import unit

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
lcd_0 = unit.get(unit.LCD, unit.PORTA)

lcd_0.fill(0x999999)
lcd_0.text('M5Stack', 0, 0, 0xff0000)
lcd_0.line(0, 10, 50, 10, 0xff0000)
lcd_0.rect(10, 10, 20, 20, 0xff0000)
lcd_0.brightness(0)
lcd_0.show_on()
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_init_display.svg">

```python
lcd_0.init_display(135, 240, 1)
```

- Initialize and Define Unit Screen Size

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_brightness.svg">

```python
lcd_0.brightness(0)
```

- Set Display Brightness

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_fill.svg">

```python
lcd_0.fill(0xff0000)
```

- Set Screen Color Fill

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_fill_input.svg">

```python
lcd_0.fill(0xff0000)
```

- Fill Specified Area with Color
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_fill_rect.svg">

```python
lcd_0.fill_rect(0, 0, 0, 0, 0xff0000)
```

- Repeat of Fill Specified Area

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_fill_rect_input.svg">

```python
lcd_0.fill_rect(0, 0, 0, 0, 0xff0000)
```

- Repeat of Fill Specified Area
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_flip.svg">

```python
lcd_0.rotate(4)
```

- Set screen rotation
  - Flip(1~6)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_hline.svg">

```python
lcd_0.hline(0, 0, 0, 0xff0000)
```

- Draw a horizontal line

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_hline_input.svg">

```python
lcd_0.hline(0, 0, 0, 0xff0000)
```

- Draw a horizontal line (duplicate entry)
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_line.svg">

```python
lcd_0.line(0, 0, 0, 0, 0xff0000)
```

- Draw a straight line from point to point

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_line_input.svg">

```python
lcd_0.line(0, 0, 0, 0, 0xff0000)
```

- Draw a straight line from point to point (duplicate entry)
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_pixel.svg">

```python
lcd_0.pixel(0, 0, 0xff0000)
```

- Draw a pixel

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_pixel_input.svg">

```python
lcd_0.pixel(0, 0, 0xff0000)
```

- Draw a pixel (duplicate entry)
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_rect.svg">

```python
lcd_0.rect(0, 0, 0, 0, 0xff0000)
```

- Draw a square

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_rect_input.svg">

```python
lcd_0.rect(0, 0, 0, 0, 0xff0000)
```

- Draw a square (duplicate entry)
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_rotate.svg">

```python
lcd_0.rotate(0)
```

- Set rotation angle (0, 90, 180, 270)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_show_on.svg">

```python
lcd_0.show_on()
```

- Turn on the device

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_sleep.svg">

```python
lcd_0.sleep(0)
```

- Set sleep time

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_text.svg">

```python
lcd_0.text('', 0, 0, 0xff0000)
```

- Draw text

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_text_input.svg">

```python
lcd_0.text('', 0, 0, 0xff0000)
```

- Draw text (duplicate entry)
  - plette
  - RGB
  - Hex

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_vline.svg">

```python
lcd_0.vline(0, 0, 0, 0xff0000)
```

- Draw a vertical line

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/lcd/uiflow_block_unit_lcd_vline_input.svg">

```python
lcd_0.vline(0, 0, 0, 0xff0000)
```

- Draw a vertical line (duplicate entry)
  - plette
  - RGB
  - Hex
