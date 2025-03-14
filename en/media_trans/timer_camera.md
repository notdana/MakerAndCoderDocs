# Timer Camera

#>Function Description | Timer Camera will capture images at specified intervals and upload them to the server after burning timer firmware. Other devices in UIFlow can use Timer Camera function to get the latest frame and display it on the screen, and configure the same token as the device to get the image content of the corresponding device. 


## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/timer_camera/uiflow_block_timercam_example.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from MediaTrans.TimerCam import TimerCam

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

cam = TimerCam('08d1f96ae2f0bc54b4998407c937e99d', 0, 0, 320, 240)
cam.show()
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/timer_camera/uiflow_block_timercam_init.svg">

```python
from MediaTrans.TimerCam import TimerCam
cam = TimerCam('08d1f96ae2f0bc54b4998407c937e99d', 0, 0, 320, 240)
```

- Initialize the TimerCAM image display service, and pass in the device token.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/timer_camera/uiflow_block_timercam_show.svg">

```python
cam.show()
```

- Enable image display


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/timer_camera/uiflow_block_timercam_hide.svg">

```python
cam.hide()
```

- Image hiding

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/timer_camera/uiflow_block_timercam_delete.svg">

```python
cam.delete()
```

- Release TimerCAM Image Display Service

