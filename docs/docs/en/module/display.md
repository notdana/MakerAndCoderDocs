# Module13.2 Display

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/display/uiflow_block_display_screen_set_bgcolor.svg">

```python
setScreenColor(0xff0000, type=hdmi)
```

- Set the background color of the screen to red.
  - Red: Indicates that the selected color is red. The system uses default color encoding to fill the screen background.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/display/uiflow_block_display_screen_set_bgcolor_input.svg">

```python
setScreenColor(0xff0000, type=hdmi)
```

- Use a color palette to choose the background color, then set the screen background to the selected color.
  - Palette: Provides a color selection tool or predefined colors for you to choose from. The current selection is red (Red).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/display/uiflow_block_display_screen_set_bgcolor_rgb.svg">

```python
setScreenColor(0x000000, type=hdmi)
```

- Precisely set the screen background color using RGB (Red, Green, Blue) values.
    - R: The value of the red channel, ranging from 0 to 255. A value of 0 means no red.
    - G: The value of the green channel, ranging from 0 to 255. A value of 0 means no green.
    - B: The value of the blue channel, ranging from 0 to 255. A value of 0 means no blue.
    - In this example, all three RGB channels are set to 0, meaning the screen background will be set to black.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/display/uiflow_block_display_screen_set_rotate.svg">

```python
hdmi.setRotation(0)
```

- Set the screen's rotation mode.
  - 0: The rotation mode parameter, where the current value of 0 indicates the default mode with no rotation. If set to other values like 1, 2, or 3, the screen will rotate 90 degrees, 180 degrees, or 270 degrees, respectively.