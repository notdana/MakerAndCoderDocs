# Echo STT

#>Function Description|Atom Echo will upload the text information to the server after burning the STT firmware, in addition to printing out the text information on the serial port when converting the text to voice. Other devices can use Echo STT Block in UIFlow to get the corresponding STT text by configuring the same token as the device.

## Get Toekn

Before using the function, you need to use [M5Burner](/en/uiflow/m5burner/intro) to flash the STT firmware onto the Atom Echo and obtain the Token (this field is required to initialize the Echo STT remote feature in UIFlow).

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_get_token_01.jpg" width="70%">
<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_get_token_02.jpg" width="70%">
<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_get_token_03.jpg" width="70%">


## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from echo import Echo
import wifiCfg

setScreenColor(0x222222)
stt_data = None

wifiCfg.autoConnect(lcdShow=False)

def echo_callback(*args):
  global stt_data
  stt_data = args[0]
  print(stt_data)
  pass


echo = Echo(str('500291857fbc58d4336dbe4e30d49797'))
echo.set_callback(echo_callback)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_init.svg">

```python
from echo import Echo
echo = Echo(str('500291857fbc58d4336dbe4e30d49797'))
echo.set_callback(echo_callback)
```

- Initialize the Echo STT data fetch function and configure the matching device token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_get_text.svg">

```python
echo.recv_text
```

- Get the returned STT text

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/echo_stt/uiflow_block_echo_stt_recv_data.svg">

```python

def echo_callback(*args):
  global stt_data
  stt_data = args[0]
  print(stt_data)
  pass
```

- New STT text message callback function

