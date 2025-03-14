# IoT Base Catm

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_check_gprs_network_registration.svg">

```python
catmiot.get_gprs_network_registration()
```

- Check whether the device is registered in the GPRS network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_check_network_registration.svg">

```python
catmiot.get_network_registration()
```

- Check whether the device is registered in a regular network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_check_single_quality.svg">

```python
catmiot.get_single_quality()
```

- Check the current signal quality of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_check_status.svg">

```python
catmiot.check_status()
```

- Check the status of the module to see if it is functioning properly.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_coap_delete.svg">

```python
catmiot.delete_coap()
```

- Send a DELETE request via the CoAP protocol to delete resources on the server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_coap_get.svg">

```python
catmiot.coap_request('/m5stack-get')
```

- Send a GET request via the CoAP protocol to retrieve resources from the specified URL.
  - /m5stack-get: The specified URL path from which to retrieve resources.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_coap_init.svg">

```python
catmiot.coap_to_connect('120.77.157.90', 5683)
```

- Initialize a connection to the specified IP address and port for CoAP protocol communication.
  - IP: 120.77.157.90
  - Port: 5683

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_coap_post.svg">

```python
catmiot.coap_request('/m5stack-post', 2, '')
```

- Send a POST request via the CoAP protocol to the specified URL.
  - URL: /m5stack-post
  - Payload: Data payload to be sent.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_disable_power_save_mode.svg">

```python
catmiot.power_save_mode(0, 0, 0, 0, False)
```

- Disable the device's power-saving mode to ensure it maintains high-performance operation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_disconnect_server.svg">

```python
catmiot.disconnect_server()
```

- Disconnect the device from the current HTTP service.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_enable_pdp_context.svg">

```python
catmiot.enable_PDP_context()
```

- Enable the PDP context, typically used for GPRS or LTE network communication, ensuring that the data transmission context is established.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_ezdata_async_get_value.svg">

```python
catmiot.get_ezdata(ezdata_get_kslNzcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Retrieve data from the specified topic.
  - Token: dCtdfg3u5id72J8YCubqu16zMqQunDQh

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_ezdata_remove.svg">

```python
catmiot.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

- Delete the specified topic from the remote server.
  - Token: dCtdfg3u5id72J8YCubqu16zMqQunDQh

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_ezdata_save.svg">

```python
catmiot.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

- Save data to the specified topic and authenticate with the specified token.
  - Token: dCtdfg3u5id72J8YCubqu16zMqQunDQh
  - Mode: Single (indicating single data save mode).
  - Data: The data to be saved.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_get_ccid.svg">

```python
catmiot.get_CCID()
```

- Get the current SIM card's CCID (Integrated Circuit Card Identifier), which is the unique identifier for the SIM card.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_get_imei.svg">

```python
catmiot.get_IMEI()
```

- Get the device's IMEI (International Mobile Equipment Identity), which is the unique identifier for the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_gprs_service.svg">

```python
catmiot.gprs_service(1)
```

- Set or check the GPRS service status. Here it is set to ACTIVE, meaning GPRS service is enabled.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_http_services.svg">

```python
catmiot.http_service(1, '', '', {}, '')
```

- Send an HTTP GET request to fetch data from a remote server.
  - Method: GET (HTTP request method)
  - URL: The requested address.
  - Headers: Create a Map containing HTTP request headers.
  - Payload: For POST requests, data can be passed through this parameter.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_init_modem.svg">

```python
catmiot.init_modem(True)
```

- Start and initialize the module, preparing it for subsequent communication and data interaction.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_init.svg">

```python
catmiot.modbus_init(15, 13, 115200, 1, 1)
```

- Initialize the UART communication interface, set the TX (transmit) pin to 15, RX (receive) pin to 13, baud rate to 115200, mode to master, and slave address to 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow

_block_iotbasecatm_modbus_master_u_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

- Read the coil status from slave address 1, starting at address 1, reading 0 coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

- Read the discrete input status from slave address 1, starting at address 1, reading 0 inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

- Read data from the holding registers of slave address 1, starting at address 1, reading 0 registers. The data is treated as signed values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

- Read data from the input registers of slave address 1, starting at address 1, reading 0 registers. The data is treated as signed values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

- Write data to multiple coils of slave address 1, starting at address 1, with the output value set to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

- Write data to multiple registers of slave address 1, starting at address 1, with the register value set to 0. The data is treated as signed values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

- Write a value to a single coil of slave address 1, with the output address set to 1 and the value written as 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_master_u_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

- Write data to a single register of slave address 1, with the register address set to 1 and the value written as 0. The data is treated as signed values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_fun_status.svg">

```python
1~6,15,16
```

- Set the MODBUS function code to READ_COILS_STATUS, used to read the status of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

- Get the slave address currently in use for MODBUS communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

- Get the function code currently being executed in MODBUS operation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

- Get the quantity of values being read or written in the current MODBUS request.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

- Initialize the MODBUS slave function code as READ_COILS_STATUS to read the status of coils starting from the specified address and quantity.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

- Receive an ADU (Application Data Unit) request, indicating that data has been received from the master device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(1)
```

- Send the ADU response data buffer, responding to the master's request.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

- Update the READ_COILS_STATUS function, read the status of the specified number of coils from the starting address, and return the corresponding data list.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_check_connection.svg">

```python
catmiot.mqtt_ischeck_connect()
```

- Check the connection status of the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_connect.svg">

```python
catmiot.mqtt_to_connect('mqtt.m5stack.com', 1883, '', '', '', 120)
```

- Initialize an MQTT server connection, setting the server address, port, client ID, username, password, and keep-alive time.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_disconnect.svg">

```python
catmiot.mqtt_disconnect()
```

- Disconnect from the MQTT server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_poll.svg">

```python
catmiot.mqtt_poll()
```

- Poll for downlink messages to check if the MQTT server has any new messages sent to the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_publish.svg">

```python
catmiot.mqtt_publish('', '', 0)
```

- Publish a message to the specified MQTT topic, including the message payload and QoS (Quality of Service) setting.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_sub.svg">

```python
catmiot.mqtt

_subscribe('', iotbasecatm_mqtt_cb, 0)
```

- Subscribe to the specified MQTT topic and set the QoS (Quality of Service) level.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_sub_cb.svg">

```python
def iotbasecatm_mqtt_cb(catm_mq_topic, catm_mq_payload):
  global ezdata_value1, catm_topic, catm_msg
  catm_topic = catm_mq_topic
  catm_msg = catm_mq_payload
  pass
```

- Set the callback function for when an MQTT topic subscription receives a message, handling the received topic and message.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_mqtt_unsubscribe.svg">

```python
catmiot.mqtt_unsubscribe('')
```

- Unsubscribe from the specified MQTT topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_network_active.svg">

```python
catmiot.network_active(0, 1)
```

- Activate the specified network ID and set its action to active.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_network_ip_id.svg">

```python
catmiot.get_network_ip(0)
```

- Retrieve the IP address of the specified network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_power_down_module.svg">

```python
catmiot.poweroff()
```

- Power off the module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_power_save_mode.svg">

```python
catmiot.power_save_mode(0, 10, 0, 5)
```

- Enable power-saving mode and set the periodic TAU (time interval) and active time period.
    - Periodic-TAU: Set in units of 10 minutes, 10 means the wake-up interval is 10 x 10 minutes, or 100 minutes.
    - Active Time: Set in units of 2 seconds, 5 means the device will remain active for 10 seconds after waking up.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_set_echo_mode.svg">

```python
catmiot.set_command_echo_mode(0)
```

- Set the command echo mode to OFF, i.e., disable command echoing.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_show_pdp_address.svg">

```python
catmiot.show_PDP_address()
```

- Display the PDP (Packet Data Protocol) address, typically used for checking the network connection status of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_any.svg">

```python
modbus._mdbus_uart.any()
```

- Check if there is any remaining data in the UART buffer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_read.svg">

```python
modbus._mdbus_uart.read()
```

- Read all available data from the UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_readline.svg">

```python
modbus._mdbus_uart.readline()
```

- Read one line of data from the UART until encountering a newline character (typically \n).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

- Read a specified number of characters from the UART, here set to read 10 characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_write.svg">

```python
modbus._mdbus_uart.write('')
```

- Write the specified data to the UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

- Write one line of data to the UART, usually accompanied by a newline character (\n).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/iot_base_catm/uiflow_block_iotbasecatm_uart_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```

- Write a raw data list to the UART.
  - Here, a list is created containing three values 0, 0, 0, indicating that these values will be sent via UART.

