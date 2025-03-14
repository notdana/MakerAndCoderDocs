# Tencent


#>Create products and devices|Before using the UIFlow Tencent function, please complete the creation of products and devices through the [Tencent Cloud IoT Development Platform](https://cloud.tencent.com/login?s_url=https%3A%2F%2Fconsole.cloud.tencent.com%2Fiotexplorer).

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_example.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from IoTcloud.Tencent import Tencent
import time
import unit

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
env20 = unit.get(unit.ENV2, unit.PORTA)

temp = None
humid = None

label0 = M5Label('温度:', x=15, y=25, color=0x000, font=FONT_UNICODE_24, parent=None)
label4 = M5Label('下发数据:', x=15, y=123, color=0x000, font=FONT_UNICODE_24, parent=None)
label1 = M5Label('湿度:', x=15, y=71, color=0x000, font=FONT_UNICODE_24, parent=None)
down_link_data = M5Label('text', x=5, y=165, color=0x000, font=FONT_MONT_14, parent=None)
label2 = M5Label('Text', x=124, y=33, color=0x000, font=FONT_MONT_14, parent=None)
label3 = M5Label('Text', x=124, y=79, color=0x000, font=FONT_MONT_14, parent=None)

def tencent_fun(property_data):
  global temp, humid
  down_link_data.set_text(str(property_data))
  pass


down_link_data.obj.set_long_mode(lv.label.LONG.BREAK)
down_link_data.obj.set_size(320, 100)
tencent = Tencent(product_id='xxxxx', device_name='xxxxx', username='xxxxxxxxxx;12010126;YWLY7;1810721745', password='d7201f1da56972d46ffb9498a86d08ed51644d8d;hmacsha1', port=1883, keepalive=30)
tencent.subscribe_property_msg(tencent_fun)
tencent.start()
while True:
  temp = env20.temperature
  humid = env20.humidity
  label2.set_text(str(temp))
  label3.set_text(str(humid))
  tencent.publish_property_msg(temperature=temp,humidity=humid)
  wait(5)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_init.svg">

```python
from IoTcloud.Tencent import Tencent
tencent = Tencent(product_id='', device_name='', username='', password='', port=1883, keepalive=0)
```

- Initialize client

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_start.svg">

```python
tencent.start()
```

- Start client connect


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_publish.svg">

```python
tencent.publish(topic,msg)
```

- publish messages

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_publish_property_msg.svg">

```python
tencent.publish_property_msg(temperature=temp,humidity=humid)
```

- publish property messages:
  - The key-value is sent in the form of key-value, in which the key value needs to be consistent with the identifier in the customized function. When the device is running, the user can view the uplink data of the device in the device log.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_sub.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_get_topic_data.svg">

```python
def fun_subscribe_(topic_data):
  # global params
  print(topic_data)
  pass

tencent.subscribe(str('subscribe'), fun_subscribe_)
```

- message subscribe callback

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_sub_msg.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/tencent/uiflow_block_tencent_get_property_topic_data.svg">


```python
def tencent_fun(property_data):
  # global params
  print(property_data)
  pass

tencent.subscribe_property_msg(tencent_fun)
```

- property message subscribe callback

