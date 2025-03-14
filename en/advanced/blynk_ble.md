# Blynk BLE

Connect to Blynk App via BLE to achieve wireless control from mobile phone. Note: Only models with PSRAM (e.g. M5Fire, M5Core2) are supported. This function only supports Blynk legacy, the new version of Blynk no longer provides BLE support.

## Example

1.Create a new project in Blynk legacy, select ESP32 Dev Board, select the access method as BLE, and record AUTH TOKEN. follow the steps below to add the components, of which BLE connection is a necessary component.

2.Use Blynk to control the color and brightness of M5StackFire's RGB light bar and display it on the screen in real time.


## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_init.svg">

```python
from ble import blynk
blynk.init('Device Name', 'Token', blynk.BLE)
```

- Initialize the blynk configuration, enter the device name and the token for the app.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_event_write.svg">

```python
def blynk_write_all(*args):
  global msg, num
  num, msg = args[0], args[1]
  pass

blynk.handle_event('write v*', blynk_write_all)
```

- Receive data from the app side to be written to the specified virtual port, if not specified set to V*.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_event_read.svg">

```python

def blynk_read_all(*args):
  global num
  num = args[0]
  pass

blynk.handle_event('read v*', blynk_read_all)
```

- Read the virtual port number specified on the App side

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_notify.svg">

```python
blynk.notify('')
```

- Send system-level message notifications to the App

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_on_event.svg">

```python
def blynk_connected():
  # global params
  print('connected')
  pass


blynk.handle_event('connected', blynk_connected)
```

- Thing listens to callback function registration, supports events.
  - connected
  - disconnected


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_tweet.svg">

```python
blynk.tweet('')
```

- Send message notifications to Twitter clients


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/blynk_ble/uiflow_block_blynk_virtual_write.svg">

```python
blynk.virtual_write(1, '')
```

- Write data to the virtual port number

