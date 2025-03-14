# Atom DTU LoRaWAN 470

## Example

> This program connects to the network, sends, and receives data via the LoRaWAN protocol. After initialization, the device attempts to join the network in OTAA mode, with the RGB light brightness showing the connection status. Once connected, it sends data every 5 seconds and checks for downlink data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_atomic_base_lorawan_470_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.DTU_LoRaWAN import DTU_LoRaWAN
import time

j = None

rgb.setColorAll(0xcc6600)
dtu_lora470 = DTU_LoRaWAN()
dtu_lora470.set_join_mode(0)
dtu_lora470.config_OTAA('2fd1549588a2f196', '00000000000000000000000000000000', '059d230cf60aaf212783b4b7e801a389')
dtu_lora470.set_frequency_band_mask('0400')
dtu_lora470.set_rx_window_param(0, 0, 505300000)
dtu_lora470.set_class_mode(2)
dtu_lora470.set_uplink_downlink_mode(1)
dtu_lora470.join(1, 1, 8, 10)
rgb.setColorAll(0xff6666)
while not dtu_lora470.check_join_status():
  print('waiting join....')
  for j in range(101):
    rgb.setBrightness(j)
    wait_ms(10)
  for j in range(100, -1, -1):
    rgb.setBrightness(j)
    wait_ms(10)
print('connected!')
rgb.setBrightness(100)
rgb.setColorAll(0x33ff33)
while True:
  dtu_lora470.send_data('012345678', 1, 15)
  print(dtu_lora470.check_downlink_data())
  wait(5)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_init.svg">

```python
dtu_lora470 = DTU_LoRaWAN()
```

- Initializes the LoRaWAN 470 DTU module, preparing the device for LoRa communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_any.svg">

```python
modbus._mdbus_uart.any()
```

- Checks if there is any unprocessed cached data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_check_downlink_data.svg">

```python
dtu_lora470.check_downlink_data()
```

- Checks and receives downlink data from the gateway, typically used to receive network instructions or information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_check_join_status.svg">

```python
dtu_lora470.check_join_status()
```

- Checks if the device has successfully joined the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_check_sent_status.svg">

```python
dtu_lora470.check_uplink_status()
```

- Checks the status of the uplink data sent by the device to confirm successful transmission.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_config.svg">

```python
dtu_lora470.set_frequency_band_mask('0001')
dtu_lora470.set_rx_window_param(0, 0, 505300000)
dtu_lora470.set_class_mode(0)
dtu_lora470.set_uplink_downlink_mode(1)
```

- Configures the frequency band mask, RX window parameters, receive frequency, and data rate (e.g., RX1 and RX2 parameters).
- Sets the device operating mode (Class A) and the frequency mode for uplink and downlink communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_config_mode.svg">

```python
dtu_lora470.config_OTAA('', '', '')
```

- Configures the device in OTAA (Over-The-Air Activation) mode with the device EUI, app key, and app EUI.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_get_abp_config.svg">

```python
dtu_lora470.get_ABP_config()
```

- Retrieves the device's ABP (Activation By Personalization) configuration information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_get_otaa_config.svg">

```python
dtu_lora470.get_OTAA_config()
```

- Retrieves the device's OTAA configuration information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_join_start.svg">

```python
dtu_lora470.join(1, 1, 8, 1)
```

- Initiates the process to join the LoRaWAN network. Allows setting the auto-join mode, interval (in seconds), and maximum number of attempts.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_join_stop.svg">

```python
dtu_lora470.join(0)
```

- Stops the network joining process.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read.svg">

```python
dtu_lora470.read()
```

- Reads all available data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_readline.svg">

```python
dtu_lora470.readline()
```

- Reads data line by line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read_characters.svg">

```python
dtu_lora470.read(10)
```

- Reads a specified number of characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read_coils.svg">

```python
dtu_lora470.read_coils(1, 1, 0)
```

- Reads the coil status using the Modbus protocol, specifying the slave address, start address, and number of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read_discrete_inputs.svg">

```python
dtu_lora470.read_discrete_inputs(1, 1, 0)
```

- Reads the status of discrete inputs, specifying the slave address, start address, and number of inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read_holding_registers.svg">

```python


dtu_lora470.read_holding_registers(1, 1, 0, True)
```

- Reads holding registers, specifying the slave address, start address, and number of registers, with an option to read signed or unsigned values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_read_input_registers.svg">

```python
dtu_lora470.read_input_registers(1, 1, 0, True)
```

- Reads input registers, specifying the slave address, start address, and number of registers, with an option to read signed or unsigned values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_receive_data.svg">

```python
dtu_lora470.receive_data()
```

- Receives downlink data from the buffer, typically used to process messages sent by the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_send_data.svg">

```python
dtu_lora470.send_data('')
```

- Sends a data payload with an option to use confirmation mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_set_join_mode.svg">

```python
dtu_lora470.set_join_mode(0)
```

- Sets the network join mode, such as OTAA (Over-The-Air Activation).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_set_uplink_app_port.svg">

```python
dtu_lora470.set_uplink_app_port(1)
```

- Sets the uplink application port, ranging from 1 to 233.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write.svg">

```python
dtu_lora470.write('')
```

- Writes data to the UART port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_line.svg">

```python
dtu_lora470.write(''+"\r\n")
```

- Writes a line of data to the UART port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_multiple_coils.svg">

```python
dtu_lora470.write_multiple_coils(1, 1, 0)
```

- Writes multiple coil states to a Modbus device, specifying the start address and output values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_multiple_registers.svg">

```python
dtu_lora470.write_multiple_registers(1, 1, 0, True)
```

- Writes multiple register values to a Modbus device, specifying the start address, register values, and support for signed data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_raw_data.svg">

```python
dtu_lora470.write(bytes([0, 0, 0]))
```

- Writes raw data to the UART port, with data passed as a list.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_single_coil.svg">

```python
dtu_lora470.write_single_coil(1, 1, 0)
```

- Writes the state of a single coil on a Modbus device, specifying the output address and value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_470/uiflow_block_base_lorawan470_write_single_register.svg">

```python
dtu_lora470.write_single_register(1, 1, 0, True)
```

- Writes a value to a single register on a Modbus device, specifying the register address and value, with support for signed data.
