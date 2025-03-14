# Module COMX NB IoT

## Example

#> Connect to the specified CoAP server with IP address 120.77.157.90 and port 5683 via NB-IoT module, then sequentially send a GET request, a POST request with `post-test` data, and a PUT request with `put-test` data, all using plain text format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_comx_nbiot_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from comx.nbiot import NBIoT

setScreenColor(0x222222)

nb = NBIoT(tx=13, rx=5)
if nb.coap_connect('120.77.157.90', 5683):
  print(nb.coap_get('/m5stack-get'))
  print(nb.coap_post('/m5stack-post', 'post-test', content_format=0))
  print(nb.coap_put('/m5stack-put', 'put-test', content_format=0))
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_check_gprs_network_registration.svg">

```python
nb.get_gprs_network_registration()
```

- Checks the GPRS network registration status, returns whether the device has successfully registered to the GPRS network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_check_network_registration.svg">

```python
nb.get_network_registration()
```

- Checks the network registration status, returns whether the device has successfully registered to any network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_check_single_quality.svg">

```python
nb.get_single_quality()
```

- Checks the signal quality, returns the current network signal strength to assess the reliability of the connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_check_status.svg">

```python
nb.check_status()
```

- Checks the module status, returns the current operating status of the device to determine if it is working properly.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_coap_connect_ip.svg">

```python
nb.coap_connect('', 5683)
```

- Connects to the specified IP address and port using the CoAP protocol. CoAP (Constrained Application Protocol) is a lightweight protocol commonly used for data transfer between IoT devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_coap_destroy.svg">

```python
nb.coap_destroy()
```

- Disconnects from the CoAP server and destroys the CoAP session.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_coap_get.svg">

```python
nb.coap_get('')
```

- Sends a GET request to the specified URL to retrieve data, with an option to use a secure connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_coap_post.svg">

```python
nb.coap_post('', '', content_format=0)
```

- Sends a POST request to the specified URL with the data provided, specifying the content format (e.g., plain text), with an option to use a secure connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_coap_put.svg">

```python
nb.coap_put('', '', content_format=0)
```

- Sends a PUT request to the specified URL to upload data, specifying the content format, with an option to use a secure connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_init.svg">

```python
NBIoT(tx=13, rx=5)
```

- Initializes the NB-IoT module by setting the TX and RX pin numbers used for serial communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_check_connection.svg">

```python
nb.mqtt_check_connection()
```

- Checks the current MQTT connection status to confirm whether the device is successfully connected to the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_connect.svg">

```python
nb.mqtt_connect('', 1883, '', '', '', 0)
```

- Connects to the specified MQTT server using the provided port, client ID, username, password, and keepalive interval. The common MQTT port is 1883.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_disconnect.svg">

```python
nb.mqtt_disconnect()
```

- Disconnects from the current MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_poll.svg">

```python
nb.mqtt_poll()
```

- Polls for messages from the server, i.e., checks if the server has sent any new messages to the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_publish.svg">

```python
nb.mqtt_publish('', '', 0)
```

- Publishes a message to the specified MQTT topic. The content of the message is specified by the payload, and QoS (Quality of Service) defines the reliability level of the message transmission.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_sub.svg">

```python
nb.mqtt_subscribe('', nbiot_mqtt_cb, 0)
```

- Subscribes to the specified MQTT topic and sets the Quality of Service level for message transmission. The device will receive all messages on this topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_sub_cb.svg">

```python
def nbiot_mqtt_cb(nb_mq_topic, nb_mq_payload):
  global nb_topic, nb_msg, nb
  nb_topic = nb_mq_topic
  nb_msg = nb_mq_payload
  pass
```

- Sets a callback function when subscribing to a specific topic. `nb_topic` is the topic variable, and `nb_msg` is the message variable. The corresponding action will be executed when a message is received on the subscribed topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_mqtt_unsubscribe.svg">

```python
nb.mqtt_unsubscribe('')
```

- Unsubscribes from the specified MQTT topic, so the device will no longer receive messages on this topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_power_down_module.svg">

```python
nb.poweroff()
```

- Powers off the NB-IoT module, entering a low-power state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_reset

_module.svg">

```python
nb.reset()
```

- Resets the NB-IoT module, causing it to restart and return to its initial state.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_nb_iot/uiflow_block_nbiot_set_echo_mode.svg">

```python
nb.set_command_echo_mode(0)
```

- Sets the command echo mode, which can be enabled or disabled. The echo mode determines whether the module returns the original command string after receiving a command.