# Base LAN 

## Example

> Initialize a TCP server, establish a connection with a specified IP and port, and continuously send randomly generated data packets. Also, monitor for available packets and print the received packet size.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module
import time

setScreenColor(0x222222)

counter = None

lan = module.get(module.LANBASE)

import random

counter = 0
print('Start the TCP Server')
print((str('Local IP address: ') + str((lan.local_ip()))))
lan.tcp_udp_config('192.168.1.97', 55005, 1, 1)
print('TCP Connected')
print((str('Remote IP address: ') + str((lan.remote_ip()))))
while True:
  counter = random.randint(100000, 999999)
  lan.tcp_send_packet(str(counter))
  wait(1)
  if lan.is_available_packet(1):
    print((str('TCP receive packet size: ') + str((lan.tcp_receive_packet(0)))) )
  wait(1)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_available_packet.svg">

```python
lan.is_available_packet(1)
```

- This block indicates that the currently available packet protocol is TCP.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_ezdata_async_get_value.svg">

```python
 lan.get_ezdata(ezdata_get_fOkSZcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Get values from a specified topic and verify using the provided token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_ezdata_remove.svg">

```python
lan.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Remove data associated with the specified topic and verify using the token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_ezdata_save.svg">

```python
lan.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

- Save a value to the specified topic, also using the token for verification. A save mode (like Single) can be chosen.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_get_data.svg">

```python
req.text
```

- Fetch data from the LAN.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_get_if_config.svg">

```python
lan.get_if_config()
```

- Check if the configuration exists or fetch the current configuration.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_get_status_code.svg">

```python
req.status_code
```

- Fetch the status code and return an integer value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_http_request.svg">

```python
try:
    req = lan.http_request(method='GET', url='', headers={})
    gc.collect()
    req.close()
  except:
    pass
```

- Method: Specify the HTTP request method, such as GET.
- URL: The URL address to request.
- Headers: Set request headers using a map.
- Data: Send data via a map.
- Success and Fail: Define actions for successful or failed requests.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_init.svg">

```python
lan.tcp_udp_config('', 0, 1, 1)
```

- remote IP: The remote device's IP address.
- port: Communication port.
- socket type: Choose the communication protocol (TCP or UDP).
- machine type: Specify whether it's a server or client.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_local_ip.svg">

```python
lan.local_ip()
```

- Fetch the local device's IP address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_init.svg">

```python
lan.modbus_init(15, 5, 115200, 1, 1)
```

- bandrate: Set the baud rate, here it's 115200.
- mode: Choose between master or slave device mode.
- slave addr: Set the slave device's address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

- slave address: Read from the slave device's address.
- starting address: Start reading at the register address.
- coil qty: Quantity of coils to read.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

- Read data from the slave device's discrete input registers.
    - slave address: The slave device's address.
    - starting address: The register address to start reading from.
    - input qty: The number of inputs to read.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

- Read data from the slave device's holding registers.
    - slave address: The slave device's address.
    - starting address: The register address to start reading from.
    - register qty: The number of registers to read.
    - signed: Specify whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

- Read data from the slave device's input registers.
    - slave address: The slave device's address.
    - starting address: The register address to start reading from.
    - register qty: The number of registers to read.
    - signed: Specify whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

- Write data to multiple coil registers on the slave device.
    - slave address: The slave device's address.
    - starting address: The register address to start writing to.
    - output value: The output value to write.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

- Write data to multiple holding registers on the slave device.
    - slave address: The slave device's address.
    - starting address: The

 register address to start writing to.
    - register value: The register value to write.
    - signed: Specify whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

- Write data to a single coil register on the slave device.
    - slave address: The slave device's address.
    - output address: The coil register's address.
    - output value: The value to write.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_master_u_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

- Write data to a single holding register on the slave device.
    - slave address: The slave device's address.
    - register address: The register's address.
    - register value: The register value to write.
    - signed: Specify whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_fun_status.svg">

```python
lan.modbus_init(15, 5, 115200, 1, 1)
```

- Set the function code to specify the Modbus command.
    - READ_COILS_STATUS: The function code to read coil status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

- Fetch the slave device's address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

- Fetch the current function code.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

- Fetch the quantity of data, used to query the number of registers to read/write.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

- Initialize the function code and related parameters.
    - READ_COILS_STATUS: The function code to read coil status.
    - start addr: Start address.
    - quantity: The number of coils to read or operate.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

- Receive an ADU (Application Data Unit) request, used for data exchange between Modbus master and slave.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(1)
```

- Send ADU response data, providing response data to the Modbus master.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

- Update the function's data information.
    - start addr: The start address to operate on.
    - quantity: The quantity of data to update.
    - value: The actual value to update.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_check_connection.svg">

```python
lan.mqtt_is_connect()
```

- Check the connection status with the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_connect.svg">

```python
lan.mqtt_connect()
```

- Connect to the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_disconnect.svg">

```python
lan.mqtt_disconnect()
```

- Disconnect from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_init.svg">

```python
lan.mqtt_config('mqtt.m5stack.com', 1883, '', '', '', 120)
```

- Initialize the MQTT connection.
  - mqtt.m5stack.com: Server address.
  - port 1883: Communication port.
  - client id: Client identifier.
  - username: Username.
  - password: Password.
  - keepalive 120: Heartbeat time (seconds) to maintain the connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_poll.svg">

```python
  lan.mqtt_poll_loop()
```

- Poll for downstream messages received from the MQTT server, checking for new messages sent to the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_publish.svg">

```python
lan.mqtt_publish('', '', 0)
```

- Publish a message to the specified topic. The device can send messages to other devices subscribed to the same topic.
  - topic: The topic to publish the message to.
  - payload: The message content to send.
  - QoS: Quality of Service level (typically 0 means the message is sent at most once, with no acknowledgment required).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_sub.svg">

```python
lan.mqtt_subscribe('', lan_base_mqtt_cb, 0)
```

- Subscribe to a topic to receive messages published under that topic.
    - topic: The topic to subscribe to. Once subscribed, the device will receive messages from that topic.
    - QoS: Control the Quality of Service level for the subscription.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_mqtt_sub_cb.svg">

```python
def lan_base_mqtt_cb(lan_mq_topic, lan_mq_payload):
  global ezdata_value1, lan_topic, lan_msg
  lan_topic = lan_mq_topic
  lan_msg = lan_mq_payload
  pass
```

- When the device receives a message from the subscribed topic, this statement triggers a callback function and displays the received topic and message content.
    - lan_topic: The topic of the received message.
    - lan_msg: The content of the received message.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_remote_ip.svg">

```python
lan.remote_ip()
```

- Set the IP address of the remote server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_set_ifconfig.svg">

```python
lan.set_if_config('192.168.1.100', '255.255.255.0', '192.168.1.1', '8.8.8.8')
```

- Configure the device's IP address, subnet mask, gateway, and DNS information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs

.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_socket_close.svg">

```python
lan.socket_close()
```

- Close the current TCP or UDP connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_tcp_receive_packet.svg">

```python
lan.tcp_receive_packet(0)
```

- Set the size of the TCP packet to receive.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_tcp_send_packet.svg">

```python
 lan.tcp_send_packet('1234')
```

- Send the specified packet content using the TCP protocol.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_any.svg">

```python
modbus._mdbus_uart.any()
```

- Check and retain data in the UART buffer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_read.svg">

```python
modbus._mdbus_uart.read()
```

- Read all data in the UART buffer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_readline.svg">

```python
modbus._mdbus_uart.readline()
```

- Read an entire line of data in the UART buffer until a newline character is encountered.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

- Read a specified number of characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_write.svg">

```python
modbus._mdbus_uart.write('')
```

- Send the specified string data via UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

- Send a line of string data via UART, usually appending a newline character at the end.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_uart_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```

- Send a raw data list via UART, commonly used for transmitting binary data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_udp_receive_packet.svg">

```python
lan.udp_receive_packet(0)
```

- Set the size of the UDP packet to receive.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lan_base/uiflow_block_lan_base_udp_send_packet.svg">

```python
lan.udp_send_packet('', 0, '')
```

- Send a UDP packet using the specified IP address, port, and payload.