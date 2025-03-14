# Atomic PoE Base

## Example
<img class="blockly_svg" src="example.svg">

```python

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_init.svg">

```python
poe.tcp_udp_config('', 0, 1, 1)
```

- Initializes the LAN connection. Configures the remote IP address, port number, and selects the communication protocol type (TCP/UDP), as well as specifying if the device is acting as a server or client.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_init.svg">

```python
poe.mqtt_config('mqtt.m5stack.com', 1883, '', '', '', 120)
```

- Initializes the MQTT server connection, specifying the server address, port, client ID, username, password, and keepalive interval.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_available_packet.svg">

```python
poe.is_available_packet(1)
```

- Checks if there are any available TCP data packets and returns the packet count.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_ezdata_async_get_value.svg">

```python
poe.get_ezdata(ezdata_get_KzSyFcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Retrieves data from a specified MQTT topic using the topic name and token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_ezdata_remove.svg">

```python
poe.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Deletes a specified topic from the MQTT server, using the topic name and token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_ezdata_save.svg">

```python
poe.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

- Saves specified data to a topic and authenticates using a token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_get_if_config.svg">

```python
poe.get_if_config()
```

- Retrieves the current network or device configuration information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_http_get.svg">

```python
poe.http_get('', True)
```

- Fetches data from a specified URL using HTTP or HTTPS, with an option to retrieve the full content.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_http_post.svg">

```python
poe.http_post('', 'application/json', '')
```

- Sends data to a specified URL using HTTP or HTTPS, with data formats like JSON or form data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_local_ip.svg">

```python
poe.local_ip()
```

- Retrieves the local IP address of the device on the LAN.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_check_connection.svg">

```python
poe.mqtt_is_connect()
```

- Checks if the device is currently connected to the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_connect.svg">

```python
poe.mqtt_connect()
```

- Connects to the specified MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_disconnect.svg">

```python
poe.mqtt_disconnect()
```

- Disconnects the current MQTT server connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_poll.svg">

```python
poe.mqtt_poll_loop()
```

- Polls for downlink messages from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_publish.svg">

```python
poe.mqtt_publish('', '', 0)
```

- Publishes a message to a specified MQTT topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_sub.svg">

```python
poe.mqtt_subscribe('', atom_poe_mqtt_cb, 0)
```

- Subscribes to a specified MQTT topic, with an option to set the Quality of Service (QoS).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_mqtt_sub_cb.svg">

```python
def atom_poe_mqtt_cb(poe_mq_topic, poe_mq_payload):
  global ezdata_value1, lan_topic, lan_msg
  lan_topic = poe_mq_topic
  lan_msg = poe_mq_payload
  pass
```

- Sets a callback function to handle messages received on the subscribed MQTT topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_remote_ip.svg">

```python
poe.remote_ip()
```

- Retrieves the remote device’s IP address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_socket_close.svg">

```python
poe.socket_close()
```

- Closes the current network socket connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_tcp_receive_packet.svg">

```python
poe.tcp_receive_packet(0)
```

- Receives data packets via TCP and reads the specified number of bytes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_tcp_send_packet.svg">

```python
poe.tcp_send_packet('1234')
```

- Sends a data packet via TCP with the specified string or numeric content.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_udp_receive_packet.svg">

```python
poe.udp_receive_packet(0)
```

- Receives data packets via UDP and reads the specified number of bytes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/poe/uiflow_block_atom_poe_udp_send_packet.svg">

```python
poe.udp_send_packet('', 0, '')
```

- Sends a data packet via UDP to a specified IP address, port number, and with specified content.