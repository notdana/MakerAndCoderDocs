# Atom DTU LoRaWAN 915

> This program uses the LoRaWAN 915 DTU module to connect to the network in OTAA mode. During the connection, the brightness of the RGB light changes to indicate the connection status. Once connected, the device sends data "012345678" every 5 seconds and checks for downlink data. Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_atomic_base_lorawan_915_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.DTU_LoRaWAN import DTU_LoRaWAN
import time

j = None

rgb.setColorAll(0xcc6600)
dtu_lora915 = DTU_LoRaWAN()
dtu_lora915.set_join_mode(0)
dtu_lora915.config_OTAA('d896e0ff00000241', '0000000000000001', '98929b92f09e2daf676d646d0f61d251')
dtu_lora915.set_frequency_band_mask('0001')
dtu_lora915.set_rx_window_param(0, 0, 923300000)
dtu_lora915.set_class_mode(2)
dtu_lora915.set_uplink_downlink_mode(1)
dtu_lora915.join(1, 1, 8, 15)
rgb.setColorAll(0xff6666)
while not dtu_lora915.check_join_status():
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
  dtu_lora915.send_data('012345678', 1, 15)
  print(dtu_lora915.check_downlink_data())
  wait(5)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_init.svg">

```python
dtu_lora915 = DTU_LoRaWAN()
```

- Initializes the LoRaWAN 915 DTU module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_any.svg">

```python
dtu_lora915.any()
```

- Retains cached data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_check_downlink_data.svg">

```python
dtu_lora915.check_downlink_data()
```

- Checks and receives downlink data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_check_join_status.svg">

```python
dtu_lora915.check_join_status()
```

- Checks the status of joining the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_check_sent_status.svg">

```python
dtu_lora915.check_uplink_status()
```

- Checks the uplink data status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_config.svg">

```python
dtu_lora915.set_frequency_band_mask('0001')
dtu_lora915.set_rx_window_param(0, 0, 923300000)
dtu_lora915.set_class_mode(0)
dtu_lora915.set_uplink_downlink_mode(1)
```

- Configures LoRaWAN parameters, including frequency mask, receive window parameters, RX1 offset, RX2 data rate, RX2 frequency, operating mode, and downlink mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_config_mode.svg">

```python
dtu_lora915.config_OTAA('', '', '')
```

- Configures OTAA mode, setting the device EUI, application key (App Key), and application EUI.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_get_abp_config.svg">

```python
dtu_lora915.get_ABP_config()
```

- Retrieves ABP (Activation By Personalization) configuration.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_get_otaa_config.svg">

```python
dtu_lora915.get_OTAA_config()
```

- Retrieves OTAA (Over-The-Air Activation) configuration.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_join_start.svg">

```python
dtu_lora915.join(1, 1, 8, 1)
```

- Initiates joining the LoRaWAN network, setting automatic join mode, interval time (seconds), and maximum number of attempts.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_join_stop.svg">

```python
dtu_lora915.join(0)
```

- Stops the process of joining the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read.svg">

```python
dtu_lora915.read()
```

- Reads all available data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_readline.svg">

```python
dtu_lora915.readline()
```

- Reads data line by line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read_characters.svg">

```python
dtu_lora915.read(10)
```

- Reads 10 characters.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read_coils.svg">

```python
dtu_lora915.read_coils(1, 1, 0)
```

- Reads coil registers from the specified slave address, starting address, and number of coils.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read_discrete_inputs.svg">

```python
dtu_lora915.read_discrete_inputs(1, 1, 0)
```

- Reads discrete input registers from the specified slave address, starting address, and number of inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read_holding_registers.svg">

```python
dtu_lora915.read_holding_registers(1, 1, 0, True)
```

- Reads holding registers from the specified slave address, starting address, and number of registers. Supports signed or unsigned data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets

/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_read_input_registers.svg">

```python
dtu_lora915.read_input_registers(1, 1, 0, True)
```

- Reads input registers from the specified slave address, starting address, and number of registers. Supports signed or unsigned data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_receive_data.svg">

```python
dtu_lora915.receive_data()
```

- Receives downlink data from the buffer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_send_data.svg">

```python
dtu_lora915.send_data('')
```

- Sends data payload, with the option for acknowledgment mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_set_join_mode.svg">

```python
dtu_lora915.set_join_mode(0)
```

- Sets the join mode, here set to OTAA (Over-the-Air Activation).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_set_uplink_app_port.svg">

```python
dtu_lora915.set_uplink_app_port(1)
```

- Sets the uplink application port, with a range from 1 to 233.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write.svg">

```python
dtu_lora915.write('')
```

- Writes data via UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_line.svg">

```python
dtu_lora915.write(''+"\r\n")
```

- Writes a line of data via UART.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_multiple_coils.svg">

```python
dtu_lora915.write_multiple_coils(1, 1, 0)
```

- Writes multiple coils to the specified slave address, with customizable start address and output values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_multiple_registers.svg">

```python
dtu_lora915.write_multiple_registers(1, 1, 0, True)
```

- Writes multiple registers to the slave address, with customizable start address and register values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_raw_data.svg">

```python
dtu_lora915.write(bytes([0, 0, 0]))
```

- Writes raw data via UART, with data passed as a list.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_single_coil.svg">

```python
dtu_lora915.write_single_coil(1, 1, 0)
```

- Writes a single coil to the specified slave address, with customizable start address and output value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/dtu_lorawan_915/uiflow_block_base_lorawan915_write_single_register.svg">

```python
dtu_lora915.write_single_register(1, 1, 0, True)
```

- Writes a single register to the slave address, with customizable start address and register value, and supports signed data.