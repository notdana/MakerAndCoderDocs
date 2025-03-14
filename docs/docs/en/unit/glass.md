# [Unit Glass](/en/unit/Glass%20Unit)

## Example

Draw text, lines, circles and wake the buzzer

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
glass_0 = unit.get(unit.GLASS_OLED, unit.PORTA)

glass_0.draw_text('M5Stack', 0, 0, 8, 1)
glass_0.draw_line(0, 10, 50, 10, 1)
glass_0.draw_circle(30, 30, 8, 1)
glass_0.disp_show()
glass_0.buzzer_freq(1000, 50)
glass_0.buzzer_ctrl(1)
wait(1)
glass_0.buzzer_ctrl(0)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_buzzer_ctrl.svg">

```python
glass_0.disp_ctrl(1)
```

- Set screen display switch
  - 1:ON
  - 0:OFF

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_buzzer_freq.svg">

```python
glass_0.buzzer_freq(1000, 50)
```

- Set buzzer frequency and duty cycle

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_colour_reverse.svg">

```python
glass_0.colour_reverse(0)
```

- Set screen color (normal display or inverted color)
  - 1: NORMAL
  - 0: REVERSE

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_disp_clear.svg">

```python
glass_0.disp_clear()
```

- Clear screen display

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_disp_ctrl.svg">

```python
glass_0.disp_ctrl(1)
```

- Set screen display switch (repeated but might be for emphasis)
  - 1: ON
  - 0: OFF

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_disp_invert.svg">

```python
glass_0.disp_invert(0, 0)
```

- Set display mode, normal or inverted
  - 1: NORMAL
  - 0: REVERSE
  - filp: (0°/180°) for flipping the display vertically

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_disp_show.svg">

```python
glass_0.disp_show()
```

- Turn on screen display switch

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_draw_circle.svg">

```python
glass_0.draw_circle(0, 0, 5, 1)
```

- Draw a circle, input radius and coordinates

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_draw_line.svg">

```python
glass_0.draw_line(0, 0, 10, 10, 1)
```

- Draw a line, input coordinates from point to point

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_draw_pixel.svg">

```python
glass_0.draw_pixel(0, 0, 1)
```

- Input pixel for display

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_draw_text.svg">

```python
glass_0.draw_text('', 0, 0, 8, 1)
```

- Display text, input coordinates and font size

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_get_button_status.svg">

```python
print(glass_0.get_button_status(0))
```

- Get the state of buttons

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/glass/uiflow_block_unit_glass_get_fw_version.svg">

```python
print(glass_0.get_firmware_version())
```

- Get the firmware version

