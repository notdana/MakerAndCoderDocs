# Atom DTU NB IoT

## Example

> This program connects to an MQTT server through the NB-IoT DTU, subscribes to the topic `SubTopic`, and prints the topic and message content upon receiving a message. When button A is pressed, a random integer is generated and published to the topic `PubTopic`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_atomic_base_nbiot_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.DTU_NB import DTU_NB

nb_topic = None
nb_msg = None
Rand = None

import random

def nbiot_mqtt_cb(nb_mq_topic, nb_mq_payload):
  global nb_topic, nb_msg, Rand
  nb_topic = nb_mq_topic
  nb_msg = nb_mq_payload
  print(nb_topic)
  print(nb_msg)
  pass

def buttonA_wasPressed():
  global nb_topic, nb_msg, Rand
  dtu_nb.mqtt_publish('PubTopic', str(Rand), 0)
  pass
btnA.wasPressed(buttonA_wasPressed)

dtu_nb = DTU_NB()
dtu_nb.mqtt_to_connect('mqtt.m5stack.com', 1883, 'm5mqtt9', '', '', 120)
print(dtu_nb.mqtt_check_connection())
print(dtu_nb.mqtt_subscribe('SubTopic', nbiot_mqtt_cb, 0))
while True:
  if (dtu_nb.mqtt_check_connection()) != None:
    Rand = random.randint(100000, 999999)
    dtu_nb.mqtt_poll()
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_init.svg">

```python
dtu_nb = DTU_NB()
```

- Initializes the NB-IoT DTU module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_init.svg">

```python
modbus = dtu_nb.modbus_init(23, 33, 115200, 1, 1)
```

- Sets up UART communication with TX, RX pins, a baud rate of 115200, master mode, and the slave address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

- Initializes Modbus function code for reading coil status, specifying the starting address and quantity.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_any.svg">

```python
modbus._mdbus_uart.any()
```

- Keeps the cache, possibly for storing data or other information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_check_gprs_network_registration.svg">

```python
dtu_nb.get_gprs_network_registration()
```

- Checks the GPRS network registration status, ensuring the device is connected to the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_check_network_registration.svg">

```python
dtu_nb.get_network_registration()
```

- Checks the network registration status, confirming if the device is registered to the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_check_single_quality.svg">

```python
dtu_nb.get_single_quality()
```

- Checks signal quality to assess the device's signal strength.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_check_status.svg">

```python
dtu_nb.check_status()
```

- Checks the module's status to ensure proper functioning.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_coap_connect_ip.svg">

```python
dtu_nb.coap_to_connect('120.77.157.90', 5683)
```

- Connects using the CoAP protocol to the specified IP address and port (in this case, 120.77.157.90 and port 5683).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_coap_destroy.svg">

```python
dtu_nb.coap_destroy()
```

- Destroys the CoAP connection to close or reset the CoAP session.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_coap_get.svg">

```python
dtu_nb.coap_get('/m5stack-get')
```

- Sends a CoAP GET request to the specified URL (e.g., /m5stack-get) with no security setting.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_coap_post.svg">

```python
dtu_nb.coap_post('/m5stack-post', '', content_format=0)
```

- Sends a CoAP POST request to the specified URL (e.g., /m5stack-post) with payload and content format as TEXT_PLAIN, no security.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_coap_put.svg">

```python
dtu_nb.coap_put('/m5stack-put', '', content_format=0)
```

- Sends a CoAP PUT request to the specified URL (e.g., /m5stack-put) with payload and content format as TEXT_PLAIN, no security.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_fun_status.svg">

```python
1-6,15-16
```

- Reads or sets the Modbus function code, in this case, selecting READ_COILS_STATUS as the function code.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

- Retrieves the slave address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

- Retrieves the current function code.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

- Retrieves the current quantity, possibly for reading the amount of data from the slave.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

- Receives an ADU (Application Data Unit) request, used for data communication in the Modbus protocol.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static

/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(1)
```

- Sends the ADU response data in the buffer, with buffer size 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

- Updates the Modbus function, currently set to READ_COILS_STATUS, specifying the start address, quantity, and updating the values list.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_check_connection.svg">

```python
dtu_nb.mqtt_check_connection()
```

- Checks the MQTT connection status, ensuring proper connectivity with the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_connect.svg">

```python
dtu_nb.mqtt_to_connect('mqtt.m5stack.com', 1883, '', '', '', 120)
```

- Connects to the MQTT server, specifying server address (e.g., mqtt.m5stack.com), port (default 1883), and options for client ID, username, password, and keepalive time in seconds.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_disconnect.svg">

```python
dtu_nb.mqtt_disconnect()
```

- Disconnects from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_poll.svg">

```python
dtu_nb.mqtt_poll()
```

- Polls for downlink messages, checking for messages sent from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_publish.svg">

```python
dtu_nb.mqtt_publish('', '', 0)
```

- Publishes a topic message to the MQTT server, specifying the topic, message content (payload), and quality of service level (QoS).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_sub.svg">

```python
dtu_nb.mqtt_subscribe('', nbiot_mqtt_cb, 0)
```

- Subscribes to a specified topic, with options for the topic name and quality of service level (QoS).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_sub_cb.svg">

```python
def nbiot_mqtt_cb(nb_mq_topic, nb_mq_payload):
  global nb_topic, nb_msg
  nb_topic = nb_mq_topic
  nb_msg = nb_mq_payload
  pass
```

- Sets a callback function for the subscription, which executes upon receiving a message on the specified topic. The message content is accessible via variables like `nb_msg`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_mqtt_unsubscribe.svg">

```python
dtu_nb.mqtt_unsubscribe('')
```

- Unsubscribes from the specified topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_power_down_module.svg">

```python
dtu_nb.poweroff()
```

- Powers off the module to conserve energy or disable it when not needed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read.svg">

```python
modbus._mdbus_uart.read()
```

- Reads all relevant information or data within the module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_readline.svg">

```python
modbus._mdbus_uart.readline()
```

- Reads one line of data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

- Reads a specified number of characters (e.g., 10 characters).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

- Reads coil status, specifying slave address, starting address, and number of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

- Reads discrete inputs, specifying slave address, starting address, and number of inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

- Reads holding registers, specifying slave address, starting address, number of registers, and whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

- Reads input registers, specifying slave address, starting address, number of registers, and whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_reset_module.svg">

```python
dtu_nb.reset()
```

- Resets the module, executing the module's reset operation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_set_echo_mode.svg">

```python
dtu_nb.set_command_echo_mode(0)
```

- Sets the command echo mode (e.g., enables or disables echo).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write.svg">

```python
modbus._mdbus_uart.write('')
```

- Writes specified content to UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

- Writes a line of content to UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

- Writes multiple coils, specifying

 the slave address, starting address, and output values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

- Writes multiple registers, specifying the slave address, starting address, register values, and whether data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```

- Writes raw data to UART, with the specified data as a list of values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

- Writes a single coil, specifying the slave address, output address, and output value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_nb_iot/uiflow_block_base_dtunb_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

- Writes a single register, specifying the slave address, register address, register value, and whether data is signed.