# Ali IoT

#>Creating Products and Devices|Refer to the [Ali IoT Platform Documentation](https://help.aliyun.com/zh/iot/getting-started/overview-7?spm=a2c4g.11186623.0.i9) to complete the product and device create.

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from IoTcloud.Ali import AliIoT
import json

import time
import unit

setScreenColor(0x222222)
env2_0 = unit.get(unit.ENV2, unit.PORTA)

shadow_msg = None
raw_msg = None
user_msg = None

label0 = M5TextBox(16, 17, "Text", lcd.FONT_Default, 0xFFFFFF, rotate=0)

def shadow_get_cb(payload):
  global shadow_msg, raw_msg, user_msg
  shadow_msg = payload
  label0.setText(str(shadow_msg))
  pass

def raw_down_cb(payload):
  global shadow_msg, raw_msg, user_msg
  raw_msg = payload
  label0.setText(str(raw_msg))
  pass

def user_get_cb(payload):
  global shadow_msg, raw_msg, user_msg
  user_msg = payload
  label0.setText(str(user_msg))
  pass


ali = AliIoT(device_id='223', product_key='a1kJNBURsxj', device_name='ENV_UNIT', region_id='cn-shanghai', password='CB57870ED7708E24863DF9A7BD8A65BE')
ali.subscribe_shadow_get_msg(shadow_get_cb)
ali.subscribe_raw_down_msg(raw_down_cb)
ali.subscribe_user_get_msg(user_get_cb)
ali.start()
while True:
  ali.publish_user_update_msg(str((json.dumps(({'Pressure':(env2_0.pressure),'Temperature':(env2_0.temperature),'Humidity':(env2_0.humidity)})))))
  ali.publish_shadow_update_msg(desiredStr='DEVICE_STATE')
  ali.publish_raw_up_msg(str('RAW MSG'))
  wait(3)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_init.svg">

```python
from IoTcloud.Ali import AliIoT
ali = AliIoT(device_id='', product_key='', device_name='', region_id='cn-qingdao', password='')
```

- Initialize client:
  - device_id, product_key, device_name: Generated after completing device creation in the Aliyun console.
  - region_id:Select the region where the service instance is located, and this information will be displayed in the AliCloud console.
  - password:After filling in the block, it will be automatically calculated and generated, and you can switch to the code workspace in UIFlow to view it.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_start.svg">

```python
ali.start()
```

- Start client connect


#>Message Publishing and Subscribing | UIFlow Ali IoT currently offers three up and down topic subscriptions, user, raw, and shadow update.<br>The role and display of different topic subscriptions in the AliCloud console will be different, for example, user can be used for general data interaction, shadow update is mainly used for synchronization of device status, raw type of topic data, allowing the user to configure custom scripts in the AliCloud console to process the data.[For more information, please see the AliCloud IoT documentation page.](https://help.aliyun.com/zh/iot/getting-started/create-a-product-and-add-a-device?spm=a2c4g.11174283.2.2.2b5b4c07rTCDtX).


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_publish_raw.svg">

```python
ali.publish_raw_up_msg(str('RAW MSG'))
```

- Publish raw messages

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_publish_shadow.svg">

```python
ali.publish_shadow_update_msg(desiredStr='DEVICE_STATE')
```

- Publish shadow messages

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_publish_user.svg">

```python
ali.publish_user_update_msg(str((json.dumps(({'Pressure':(env2_0.pressure),'Temperature':(env2_0.temperature),'Humidity':(env2_0.humidity)})))))
```

- Publish user messages


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_sub_raw.svg">

```python
def raw_down_cb(payload):
  global shadow_msg, raw_msg, user_msg
  raw_msg = payload
  pass

ali.subscribe_raw_down_msg(raw_down_cb)
```

- subscribe raw messages


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_sub_shadow.svg">

```python
def shadow_get_cb(payload):
  global shadow_msg, raw_msg, user_msg
  shadow_msg = payload
  pass

ali.subscribe_shadow_get_msg(shadow_get_cb)
```

- subscribe shadow messages

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/ali_iot/uiflow_block_aliiot_sub_user.svg">

```python
def user_get_cb(payload):
  global shadow_msg, raw_msg, user_msg
  user_msg = payload
  pass


ali.subscribe_user_get_msg(user_get_cb)
```

- subscribe user messages

