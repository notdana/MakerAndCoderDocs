# Remote

#>Introduction|Create a web page consisting of controls that can be used to remotely control M5Stack devices through the Remote feature. The page is associated with the device's API KEY, which will be stored in M5 service for a long time, and provides a fixed access link, so that users can access and share device information or control the device remotely anytime and anywhere. <br>Note:<br>1. This function requires the online version of UIFlow<br>2. When downloading and running offline, you need to add the WiFi connection program to the setup.[View the WiFi connection program description](/en/uiflow/blockly/hardwares/network)<br>3. You need to push the program before using it. You need to push the program before using it, and then you can get the QR code/URL of the access page.


## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_example.svg">


```python
from m5stack import *
from m5ui import *
from uiflow import *
remoteInit()

setScreenColor(0x111111)

x = None

def _remote_ON_OFF(x):
  if x == 1:
    rgb.setColorAll(0x3333ff)
  else:
    rgb.setColorAll(0x000000)

def _remote_Bright(x):
  rgb.setBrightness(x)


lcd.qrcode('http://flow-remote.m5stack.com/?remote=undefined', 72, 32, 176)
```


## API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_set_qrcode.svg">

```python
lcd.qrcode('http://flow-remote.m5stack.com/?remote=undefined', 72, 32, 176)
```

- Set the display position and size of the QR code of the generated web page. Note: After the web page is run for the first time, the remote parameter of the URL in the code will be automatically updated, so the API needs to be run once through UIFlow online mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_set_title.svg">

- Set the remote web page title

#>Control Variables | Except for the button control, all other controls involving input parameters need to click the gear button in the upper left corner of the block to add variables before use, and then use variables with the same name to get the incoming parameters inside their programs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_add_switch.svg">

```python
def _remote_SwitchName(x):
  pass
```

- Add toggle switch control

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_add_button.svg">

```python
def _remote_ButtonName():
  pass
```

- Adding Key Controls

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_add_slider.svg">

```python
def _remote_SliderName(x):
  pass
```

- Adding Slider Controls

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_add_label.svg">

```python
def _remote_LabelName(x):
  pass
```

- Adding Label Display Controls

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/remote/uiflow_block_remote_add_input.svg">

```python
def _remote_InputName(x):
  pass
```

- Adding Text Input Controls

