# Atom DTU Cat1

## Example Program

> This program communicates with a server using the MQTT protocol. After connecting, it subscribes to the `cat_topic` and publishes a message "hello". When a message is received on this topic, the program updates the RGB light color and prints the message content. Each time a message is received, the `cat_msg` variable is cleared, and it waits 1 second before the next loop.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_atomic_base_cat1_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.DTU_CAT1 import DTU_CAT1
import time

cat_topic = None
cat_msg = None

def cat_mqtt_cb(cat_mq_topic, cat_mq_payload):
  global cat_topic, cat_msg
  cat_topic = cat_mq_topic
  cat_msg = cat_mq_payload
  rgb.setColorAll(0xffff00)
  pass

cat = DTU_CAT1()
cat.mqtt_to_connect('mqtt.m5stack.com', 1883, 'cat1_4399', 'm5', 'm5', 120)
if cat.is_connect_mqtt():
  rgb.setColorAll(0x33cc00)
  print('MQTT Connected')
if cat.mqtt_subscribe('cat_topic', cat_mqtt_cb, 0):
  print('topic subscribed')
cat.mqtt_publish('cat_topic', 'hello', 0)
while True:
  cat.mqtt_poll()
  if cat_msg != None:
    print((str(((str(((str('message from topic: ') + str(cat_topic)))) + str(' : ')))) + str(cat_msg)))
    cat_msg = None
    rgb.setColorAll(0x33cc00)
  wait(1)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_init.svg">

```python
cat = DTU_CAT1()
```

- Initializes the CAT1 DTU module to start using it for communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_init.svg">

```python
modbus = cat.modbus_init(23, 33, 115200, 1, 1)
```

- Sets the Modbus communication baud rate to 115200, in master mode, and specifies the slave address as 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

- Initializes the Modbus function code to read coil status. You can specify the start address and quantity to read.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_check_gprs_network_registration.svg">

```python
cat.get_gprs_network_registration()
```

- Checks if the CAT1 DTU module is registered on the GPRS network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_check_network_registration.svg">

```python
cat.get_network_registration()
```

- Checks the network registration status to confirm if the module is registered to the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_check_single_quality.svg">

```python
cat.get_single_quality()
```

- Checks the current signal quality, typically to assess signal strength and stability.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_check_status.svg">

```python
cat.check_status()
```

- Checks the current status of the module to ensure it is functioning correctly or to retrieve fault information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_enable_pdp_context.svg">

```python
cat.enable_PDP_context()
```

- Enables the PDP (Packet Data Protocol) context for the CAT1 DTU module to connect to the mobile network and begin data transmission.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_ezdata_async_get_value.svg">

```python
cat.get_ezdata(ezdata_get_nOfcOcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Retrieves a value from a specified topic, using the provided token to access the data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_ezdata_remove.svg">

```python
cat.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Deletes data from a specified topic, identified by the token.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_ezdata_save.svg">

```python
cat.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

- Saves data to a specified topic. You can choose the storage mode, such as Single mode, using the token to identify the topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_get_ccid.svg">

```python
cat.get_CCID()
```

- Retrieves the CCID (Integrated Circuit Card Identifier) of the SIM card, used to identify the inserted SIM card.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_get_imei.svg">

```python
cat.get_IMEI()
```

- Retrieves the IMEI (International Mobile Equipment Identity) of the CAT1 DTU module, used for device identification.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_http_get.svg">

```python
cat.http_get('')
```

- Sends an HTTP(S) GET request to a specified URL to retrieve data from a server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_http_post.svg">

```python
cat.http_post('', 'application/json', '')
```

- Sends an HTTP(S) POST request, specifying the URL and data type (e.g., JSON), to send data to a server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_http_terminate.svg">

```python
cat.http_terminate()
```

- Terminates the current HTTP(S) connection.

Continuing with the translation:

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

- Reads the coil status from a Modbus slave, providing the slave address, start address, and the number of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

- Reads discrete input signals from a Modbus slave, providing the slave address, start address, and the number of inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

- Reads holding registers from a Modbus slave, specifying the slave address, start address, and the number of registers. You can also choose whether the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

- Reads input registers from a Modbus slave, similar to reading holding registers, but typically used for sensor data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

- Writes multiple coil states to a specified Modbus slave address. Set the slave address, start address, and output values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

- Writes multiple holding registers to a specified Modbus slave address. Set the slave address, start address, register values, and choose if the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

- Writes a single coil state to a specified Modbus slave address. Set the slave address, output address, and output value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_master_u_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

- Writes a single holding register to a specified Modbus slave address. Set the slave address, register address, register value, and choose if the data is signed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_fun_status.svg">

```python
1-6,15-16
```

- Initializes the Modbus function codes used to read coil status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

- Retrieves the current Modbus slave address in communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

- Retrieves the Modbus function code currently in use.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

- Retrieves the quantity of data requested in the Modbus query, typically associated with the number of coils or registers.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

- Receives the Application Data Unit (ADU) request from Modbus RTU. This is the data frame received from the Modbus master device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(1)
```

- Sends the ADU data response back to the Modbus master device. Here, the response is set to the value 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

- Updates the Modbus function code execution result. This function reads coil status and specifies the start address, quantity, and values in a list format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_check_connect.svg">

```python
cat.is_connect_mqtt()
```

- Checks the MQTT connection status to ensure it is connected to the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_connect.svg">

```python
cat.mqtt_to_connect('mqtt.m5stack.com', 1883, '', '', '', 120)
```

- Initializes a connection to the MQTT server at mqtt.m5stack.com, port 1883. You need to specify the client id, username, and password for authentication. The keepalive is set to 120 seconds to maintain the heartbeat interval.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_disconnect.svg">

```python
cat.mqtt_disconnect()
```

- Disconnects from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_poll.svg">

```python
cat.mqtt_poll()
```

- Polls the MQTT server to check if there is any downlink message for the client.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_publish.svg">

```python
cat.mqtt_publish('', '', 0)
```

- Publishes a message to a specified MQTT topic. You need to provide the topic, payload, and QoS (Quality of Service level, default is 0).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_sub.svg">

```python
cat.mqtt_subscribe('', cat_mqtt_cb, 0)
```

- Subscribes to a specified MQTT topic,

 providing the topic name and QoS level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_sub_cb.svg">

```python
def cat_mqtt_cb(cat_mq_topic, cat_mq_payload):
  global ezdata_value1, cat_topic, cat_msg
  cat_topic = cat_mq_topic
  cat_msg = cat_mq_payload
  pass
```

- Sets a callback function for the subscribed MQTT topic, which is triggered when a message is received for the specified topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_mqtt_unsubscribe.svg">

```python
cat.mqtt_unsubscribe('')
```

- Unsubscribes from a specified MQTT topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_power_down_module.svg">

```python
cat.poweroff()
```

- Powers off the module to enter a low-power mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_reset_module.svg">

```python
cat.reset()
```

- Resets and restarts the module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_set_echo_mode.svg">

```python
cat.set_command_echo_mode(0)
```

- Sets the command echo mode, allowing you to enable or disable it (OFF).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_any.svg">

```python
modbus._mdbus_uart.any()
```

- Reads the UART buffer to check if there is any data available.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_read.svg">

```python
modbus._mdbus_uart.read()
```

- Reads all available data from UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_readline.svg">

```python
modbus._mdbus_uart.readline()
```

- Reads data from UART until a newline character is encountered.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

- Reads a specified number of characters from UART, here set to 10 characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_write.svg">

```python
modbus._mdbus_uart.write('')
```

- Sends the specified data through UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

- Writes a complete line of data to UART, usually ending with a newline character, suitable for sending string data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_cat1/uiflow_block_dtu_cat1_uart_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```

- Writes raw data in the form of a byte list to UART, suitable for sending binary data or non-string formats.