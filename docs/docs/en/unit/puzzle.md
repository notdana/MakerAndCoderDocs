# Unit Puzzle

## Example

> Set the brightness of `puzzle_0` to 20 and continuously display the configured hexagon matrix color.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/uiflow_block_unit_puzzle_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

puzzle_0 = unit.get(unit.PUZZLE, unit.PORTA, 64)
puzzle_0.setBrightness(20)
while True:
  puzzle_0.setColor(20, 0xff0000)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/1_uiflow_block_unit_puzzle_set_color.svg">

```python
puzzle_0.setColor(1, 0xff0000)
```

- Sets the RGB color of a specific LED (numbered 1 to 64). The color can be selected from the palette.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/2_uiflow_block_unit_puzzle_set_color_from.svg">

```python
puzzle_0.setColorFrom(1, 5, 0xff0000)
```

- Sets the RGB color of a group of LEDs (from LED 1 to 5). The color can also be selected from the palette.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/3_uiflow_block_unit_puzzle_set_color_all.svg">

```python
puzzle_0.setColorAll(0xff0000)
```

- Sets the RGB color of all LEDs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/4_uiflow_block_unit_puzzle_set_brightness.svg">

```python
puzzle_0.setBrightness(20)
```

- Sets the overall brightness of the LEDs, with a range from 0 to 100.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/5_uiflow_block_unit_puzzle_set_show_lock.svg">

```python
puzzle_0.setShowLock(True)
```

- Sets whether the lock display state is enabled.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/6_uiflow_block_unit_puzzle_show.svg">

```python
puzzle_0.show()
```

- Activates the currently configured RGB LED display.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/7_uiflow_block_unit_puzzle_set_hexagon_matrix.svg">

```python
puzzle_0.setColor(20, 0xff0000)
```

- Sets the LED matrix color via an RGB color selector, adjusting the red, green, and blue values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/puzzle/8_uiflow_block_unit_puzzle_set_hexagon_matrix_rgb.svg">

```python
puzzle_0.setColor(20, 0xff0000)
```

- Configures the LED matrix color by specifying numerical values for red, green, and blue, controlling the RGB settings.