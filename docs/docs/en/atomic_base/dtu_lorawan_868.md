# Atom DTU LoRaWAN 868

## Example

> This program uses the LoRaWAN 868 DTU module to connect to the network in OTAA mode. During the connection, the RGB light indicates the status through brightness changes. Once connected, the device sends data "012345678" every 5 seconds and checks for downlink data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_atomic_base_lorawan_868_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.DTU_LoRaWAN import DTU_LoRaWAN
import time

j = None

rgb.setColorAll(0xcc6600)
dtu_lora868 = DTU_LoRaWAN()
dtu_lora868.set_join_mode(0)
dtu_lora868.config_OTAA('00bb9da5b97addf8', '00000000000000000000000000000000', '27dfe264ca33ac1957c005eb48ba4728')
dtu_lora868.set_frequency_band_mask('0001')
dtu_lora868.set_rx_window_param(0, 0, 869525000)
dtu_lora868.set_class_mode(2)
dtu_lora868.set_uplink_downlink_mode(1)
dtu_lora868.join(1, 1, 8, 10)
rgb.setColorAll(0xff6666)
while not dtu_lora868.check_join_status():
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
  dtu_lora868.send_data('012345678', 1, 15)
  print(dtu_lora868.check_downlink_data())
  wait(5)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_init.svg">

```python
dtu_lora868 = DTU_LoRaWAN()
```

- Initializes the LoRaWAN 868 DTU module for LoRaWAN communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_any.svg">

```python
dtu_lora868.any()
```

- Retains cached data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_check_downlink_data.svg">

```python
dtu_lora868.check_downlink_data()
```

- Checks and receives downlink data (data sent from the server to the device).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_check_join_status.svg">

```python
dtu_lora868.check_join_status()
```

- Checks the status of the device joining the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_check_sent_status.svg">

```python
dtu_lora868.check_uplink_status()
```

- Checks the status of uplink data (data sent from the device to the server).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_config.svg">

```python
dtu_lora868.set_frequency_band_mask('')
dtu_lora868.set_rx_window_param(0, 0, 869525000)
dtu_lora868.set_class_mode(0)
dtu_lora868.set_uplink_downlink_mode(1)
```

- Configures the frequency, window parameters, data rate, mode, etc., for LoRaWAN.
    - frequency band mask: Sets the mask for selecting the frequency band.
    - RX1 offset and RX2 freq (Hz): Sets the receive window and frequency.
    - class mode: Selects the LoRaWAN class (e.g., Class A).
    - uplink downlink: Sets the frequency mode for uplink and downlink.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_config_mode.svg">

```python
dtu_lora868.config_OTAA('', '', '')
```

- Configures the necessary parameters for OTAA mode:
    - device eui: Device identifier.
    - app key and app eui: Application key and identifier used for OTAA authentication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_get_abp_config.svg">

```python
dtu_lora868.get_ABP_config()
```

- Retrieves the configuration for ABP mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_get_otaa_config.svg">

```python
dtu_lora868.get_OTAA_config()
```

- Retrieves the configuration for OTAA mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_join_start.svg">

```python
dtu_lora868.join(1, 1, 8, 1)
```

- Initiates the process to join the LoRaWAN network.
    - open: Sets whether to automatically join the network.
    - period (seconds): Specifies the interval between join attempts.
    - maximum number of attempts: Sets the maximum number of attempts.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_join_stop.svg">

```python
dtu_lora868.join(0)
```

- Stops the current network joining process.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read.svg">

```python
dtu_lora868.read()
```

- Read all: Reads all available data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_readline.svg">

```python
dtu_lora868.readline()
```

- Read line: Reads data line by line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read_characters.svg">

```python
dtu_lora868.read(10)
```

- Reads a specified number of characters, e.g., reads 10 characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read_coils.svg">

```python
dtu_lora868.read_coils(1, 1, 0)
```

- Reads coil status from the specified slave address, setting the start address and number of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read_discrete_inputs.svg">

```python
dtu_lora868.read_discrete_inputs(1, 1, 0)
```

- Reads discrete input status from the specified slave address, setting the start address and number of inputs.

<img class="blockly_svg"

 src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read_holding_registers.svg">

```python
dtu_lora868.read_holding_registers(1, 1, 0, True)
```

- Reads holding registers from the specified slave address, setting the start address and number of registers, with support for signed or unsigned values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_read_input_registers.svg">

```python
dtu_lora868.read_input_registers(1, 1, 0, True)
```

- Reads input registers from the specified slave address, setting the start address and number of registers, with support for signed or unsigned values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_receive_data.svg">

```python
dtu_lora868.receive_data()
```

- Receives downlink data from the buffer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_send_data.svg">

```python
dtu_lora868.send_data('')
```

- Sends a data payload, setting data and confirmation mode (acknowledged or unacknowledged).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_set_join_mode.svg">

```python
dtu_lora868.set_join_mode(0)
```

- Sets the join mode, supporting OTAA (Over-the-Air Activation).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_set_uplink_app_port.svg">

```python
dtu_lora868.set_uplink_app_port(1)
```

- Sets the uplink application port, with a range from 1 to 233.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write.svg">

```python
dtu_lora868.write('')
```

- Sends data via UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_line.svg">

```python
dtu_lora868.write(''+"\r\n")
```

- Sends a line of data via UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_multiple_coils.svg">

```python
dtu_lora868.write_multiple_coils(1, 1, 0)
```

- Writes multiple coils, with slave address set to 1, start address and output values both set to 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_multiple_registers.svg">

```python
dtu_lora868.write_multiple_registers(1, 1, 0, True)
```

- Writes multiple registers, with slave address set to 1, start address set to 1, register values set to 0, and signed data set to True.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_raw_data.svg">

```python
dtu_lora868.write(bytes([0, 0, 0]))
```

- Writes raw data via UART, with data passed as a list ([0, 0, 0]).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_single_coil.svg">

```python
dtu_lora868.write_single_coil(1, 1, 0)
```

- Writes a single coil, with slave address set to 1, output address and output value both set to 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_868/uiflow_block_base_lorawan868_write_single_register.svg">

```python
dtu_lora868.write_single_register(1, 1, 0, True)
```

- Writes a single register, with slave address set to 1, register address set to 1, register value set to 0, and signed data set to True.