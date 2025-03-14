# Module COMX Cat1

## Example

#> Initialize the MQTT connection. <br>Subscribe to a specified topic and publish messages via MQTT. <br>In a loop, generate a random number as the counter value, and if the counter value differs from the previous one, publish it to the specified topic. <br>The program will display the current counter value, the messages from the subscribed topic, and the MQTT connection status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_comx_cat1_demo.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_comx_cat1_demo1.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from comx.cat1 import CAT1

setScreenColor(0x222222)

cat_topic = None
cat_msg = None
counter = None
previous = None

import random

def cat_mqtt_cb(cat_mq_topic, cat_mq_payload):
  global cat_topic, cat_msg, counter, previous, cat
  cat_topic = cat_mq_topic
  cat_msg = cat_mq_payload
  label5.setText(str(cat_topic))
  label7.setText(str(cat_msg))
  pass

print('Start Mqtt')
counter = 0
previous = 0
cat = CAT1(tx=17, rx=16)
cat.mqtt_to_connect('mqtt.m5stack.com', 1883, 'mqtt_m9', '', '', 120)
if cat.is_connect_mqtt():
  print('Connected Mqtt')
while not (cat.mqtt_subscribe('SubTopic', cat_mqtt_cb, 0)):
  cat.mqtt_unsubscribe('SubTopic')
print('Success Subscribe')
while True:
  cat.mqtt_poll()
  if counter != previous:
    cat.mqtt_publish('PubTopic', str(counter), 0)
    previous = counter
  if cat.is_connect_mqtt():
    print('Connected Mqtt')
  counter = random.randint(100000, 999999)
  print((str('counter:') + str(counter)))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_check_gprs_network_registration.svg">

```python
cat.get_gprs_network_registration()
```

- Checks the GPRS network registration status to confirm whether the device has successfully registered to the GPRS network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_check_network_registration.svg">

```python
cat.get_network_registration()
```

- Checks the network registration status to confirm whether the device has successfully registered to the network, which may include different types such as GPRS, LTE, etc.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_check_single_quality.svg">

```python
cat.get_single_quality()
```

- Checks the signal quality, returning the current network signal strength to evaluate the quality of the device's connection to the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_check_status.svg">

```python
cat.check_status()
```

- Checks the module status to obtain the current operating state of the module, confirming whether it is functioning normally.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_enable_pdp_context.svg">

```python
cat.enable_PDP_context()
```

- Enables the PDP context, which is typically used for data transmission. Once enabled, the device can communicate data over the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_ezdata_async_get_value.svg">

```python
cat.get_ezdata(ezdata_get_IklJVcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Asynchronously retrieves the value associated with a specified topic by providing the topic name and token. This operation is typically used to get specific data from the cloud or a remote server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_ezdata_remove.svg">

```python
cat.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Removes data or unsubscribes from a specified topic using the provided token. This operation is used to manage data storage or traffic, ensuring that unnecessary topics no longer consume resources.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_ezdata_save.svg">

```python
cat.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

- Saves a specified value to a topic, with authentication via token. You can choose the mode of saving data, such as single or continuous saving. This function is typically used for uploading data to the cloud or a remote server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_get_ccid.svg">

```python
cat.get_CCID()
```

- Retrieves the device's CCID (Integrated Circuit Card Identifier), a unique identifier for the SIM card, used to identify the SIM card in the mobile network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_get_imei.svg">

```python
cat.get_IMEI()
```

- Retrieves the device's IMEI (International Mobile Equipment Identity), a unique identifier for the device, used to identify the device in the mobile network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_http_get.svg">

```python
cat.http_get('')
```

- Sends an HTTP or HTTPS GET request to the specified URL to retrieve data from the server. You can specify the resource to request via the URL parameter.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_http_post.svg">

```python
cat.http_post('', 'application/json', '')
```

- Sends an HTTP or HTTPS POST request to the specified URL with JSON-formatted data, used to upload data to the server. POST requests are commonly used for submitting form data or uploading data to the server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_http_terminate.svg">

```python
cat.http_terminate()
```

- Terminates the current HTTP or HTTPS session and releases resources. This is used after data transmission to ensure the session is properly closed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_init.svg">

```python
CAT1(tx=17, rx=16)
```

- Initializes the Cat1 module's TX and RX pins, used to set the pin numbers for serial communication. This module is typically used for serial communication with the Cat1 module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_check_connect.svg">

```python
cat.is_connect_mqtt()
```

- Checks the current MQTT connection status to ensure whether the device has successfully connected to the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_connect.svg">

```python
cat.mqtt_to_connect('mqtt.m5stack.com', 1883, '', '', '', 120

)
```

- Initializes the MQTT server connection settings, including the server address (mqtt.m5stack.com), port number (1883), client ID, username, password, and keepalive time.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_disconnect.svg">

```python
cat.mqtt_disconnect()
```

- Disconnects from the MQTT server, used to end the MQTT session.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_poll.svg">

```python
cat.mqtt_poll()
```

- Checks and retrieves downstream messages, i.e., messages sent from the MQTT server to the device. This is used to receive messages.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_publish.svg">

```python
cat.mqtt_publish('', '', 0)
```

- Publishes a message to the specified MQTT topic. You can set the topic name, the message content (payload), and choose the QoS (Quality of Service) level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_sub.svg">

```python
cat.mqtt_subscribe('', cat_mqtt_cb, 0)
```

- Subscribes to a specified MQTT topic. The device will receive all messages published to this topic. You can set the topic name and choose the QoS level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_sub_cb.svg">

```python
def cat_mqtt_cb(cat_mq_topic, cat_mq_payload):
  global ezdata_value1, cat_topic, cat_msg, cat
  cat_topic = cat_mq_topic
  cat_msg = cat_mq_payload
  pass
```

- Sets the callback function for the subscribed topic. When the device receives a message from the specified topic, this callback function will be invoked to process the message. In this block, `cat_topic` represents the topic, and `cat_msg` represents the received message.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_mqtt_unsubscribe.svg">

```python
cat.mqtt_unsubscribe('')
```

- Unsubscribes from the specified MQTT topic. The device will no longer receive messages from this topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_power_down_module.svg">

```python
cat.poweroff()
```

- Powers down the module, putting it into low-power mode. This saves energy, but the module will no longer be able to perform tasks.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_reset_module.svg">

```python
cat.reset()
```

- Resets the module, similar to rebooting the device. This is typically used to restore the module to its initial state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_cat1/uiflow_block_com_cat1_set_echo_mode.svg">

```python
cat.set_command_echo_mode(0)
```

- Sets the command echo mode. When enabled, the module will echo command input after each command is executed. When disabled, the module will no longer echo command input.