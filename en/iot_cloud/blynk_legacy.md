# Blynk Legacy

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_legacy_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from IoTcloud import blynk
import unit

setScreenColor(0x222222)
env20 = unit.get(unit.ENV2, unit.PORTA)

temp_pin = None
temp = None
humid_pin = None
humid = None
spk_pin = None
spk_status = None

label0 = M5TextBox(25, 8, "UIFlow Blynk", lcd.FONT_DejaVu40, 0x00f67c, rotate=0)
label1 = M5TextBox(24, 92, "Temp:", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)
label2 = M5TextBox(25, 168, "Humid:", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)
label3 = M5TextBox(175, 97, "Text", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label4 = M5TextBox(175, 173, "Text", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)

def blynk_read_v3(v_pin):
  global temp_pin, temp, humid_pin, humid, spk_pin, spk_status
  temp_pin = v_pin
  temp = env20.temperature
  blynk1.virtual_write(temp_pin, temp)
  label3.setText(str(temp))

  pass

def blynk_read_v4(v_pin):
  global temp_pin, temp, humid_pin, humid, spk_pin, spk_status
  humid_pin = v_pin
  humid = env20.humidity
  blynk1.virtual_write(humid_pin, humid)
  label4.setText(str(humid))

  pass

def blynk_write_all(v_pin, value):
  global temp_pin, temp, humid_pin, humid, spk_pin, spk_status
  spk_pin = v_pin
  spk_status = value
  if spk_status[0] == '1':
    speaker.tone(1800, 200)

  pass

blynk1 = blynk.Blynk(token='PuCeel1XhrmWTeOZpVWlvUMQV2SfdpW1')
blynk1.handle_event('read v3', blynk_read_v3)
blynk1.handle_event('read v4', blynk_read_v4)
blynk1.handle_event('write v*', blynk_write_all)
temp = 0
humid = 0
while True:
  blynk1.run()
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_init.svg">

```python
from IoTcloud import blynk
blynk1 = blynk.Blynk(token='')
```

- Initialize client connection information.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_init_customer.svg">

```python
from IoTcloud import blynk
blynk1 = blynk.Blynk(server='', port=0, token='', heartbeat=0)
```

- Initialize client, and configure the Blynk server address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_disconnect.svg">

```python
blynk1.disconnect()
```

- Disconnect client connection.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_run.svg">

```python
blynk1.run()
```

- Update client status, which needs to be placed in the main loop.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_event_read.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_virtual_write.svg">

```python

def blynk_read_v3(v_pin):
  temp_pin = v_pin
  temp = 100
  blynk1.virtual_write(temp_pin, temp)

blynk1.handle_event('read v3', blynk_read_v3)
```

- Virtual pin read event callback function.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_event_write.svg">

```python
def blynk_write_all(v_pin, value):
  print(v_pin)
  print(value)
  pass

blynk1.handle_event('write v*', blynk_write_all)
```

- Virtual pin write event callback function.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_set_property.svg">

```python
blynk1.set_property(0, '', '')
```

- Set component properties.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_virtual_sync.svg">

```python
blynk1.virtual_sync(pin)
```

- Synchronize the status of virtual pins.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_email.svg">

```python
blynk1.email('', '', '')
```

- Send an email.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_tweet.svg">


```python
blynk1.tweet('')
```

- Send twitter msg

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_legacy/uiflow_block_iot_blynk_notify.svg">

```python
blynk1.notify('')
```

- Send APP notify

