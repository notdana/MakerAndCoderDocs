# Module COMX LoRaWAN 915

## Example

#> Use the LoRaWAN 915 module to connect to the network via OTAA mode, configure the frequency band and data rate parameters, and periodically send payload data and receive downlink data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_LoRaWAN915_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from comx.LoRaWAN import LoRaWAN_915
import time

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

flag = None

lora915 = LoRaWAN_915(tx=17, rx=16)
lora915.set_join_mode(0)
lora915.config_OTAA('', '', '')
lora915.set_frequency_band_mask('0002')
lora915.set_rx_window_param(0, 0, 923300000)
lora915.set_class_mode(2)
lora915.set_uplink_downlink_mode(2)
lora915.join(1, 1, 8, 8)
flag = False
while True:
  if not flag and lora915.check_join_status():
    flag = True
    print('Joined')
  if flag:
    lora915.send_data('M5STACK', 1, 5)
    print(lora915.check_downlink_data())
  wait(10)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_check_downlink_data.svg">

```python
lora915.check_downlink_data()
```

- Check and receive downlink data. This block is used to check whether the LoRaWAN network has sent data to the device and to receive that data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_check_join_status.svg">

```python
lora915.check_join_status()
```

- Check the device's status of joining the LoRaWAN network. This block is used to confirm whether the device has successfully joined the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_check_sent_status.svg">

```python
lora915.check_uplink_status()
```

- Check the status of uplink data. This block is used to confirm whether the device's uplink data has been successfully transmitted to the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_config.svg">

```python
lora915.set_frequency_band_mask('0001')
lora915.set_rx_window_param(0, 0, 923300000)
lora915.set_class_mode(0)
lora915.set_uplink_downlink_mode(1)
```

- Configure LoRaWAN communication parameters. This block includes the following settings:
  - frequency band mask: Sets the mask range for the frequency band, in this example from 915.2 MHz to 916.6 MHz.
  - RX window param: Configures the receive window parameters.
  - RX1 offset: Sets the frequency offset for the first receive window.
  - RX2 datarate: Sets the data rate for the second receive window (in this example SF12 BW125).
  - RX2 freq: Sets the frequency for the second receive window (in this example 923300000 Hz).
  - class mode: Sets the device's class mode (in this example, class A).
  - uplink downlink: Sets the frequency mode for uplink and downlink data (in this example, same frequency mode).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_config_mode.svg">

```python
lora915.config_OTAA('', '', '')
```

- Configure the LoRaWAN OTAA (Over The Air Activation) mode.
  - device eui: The device's EUI (unique identifier) used to uniquely identify the device in the LoRaWAN network.
  - app key: The application key used to secure communication between the device and the network.
  - app eui: The application's EUI, used to identify the application with a unique identifier.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_get_abp_config.svg">

```python
lora915.get_ABP_config()
```

- Get the configuration parameters for ABP (Activation By Personalization) mode. In ABP mode, the device directly joins the network using pre-configured keys and parameters without needing the OTAA process.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_get_otaa_config.svg">

```python
lora915.get_OTAA_config()
```

- Get the configuration parameters for OTAA mode. This block is used to read the current device's configuration in OTAA mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_init.svg">

```python
LoRaWAN_915(tx=0, rx=0)
```

- Initialize the LoRaWAN 915 MHz band with transmit (TX) and receive (RX) pins. These pins are used for communication with the LoRaWAN module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_join_start.svg">

```python
lora915.join(1, 1, 8, 1)
```

- Start the process of joining the LoRaWAN network.
  - open: Sets whether to automatically rejoin the network. When "auto join" is selected, the device will automatically attempt to rejoin if the connection is lost.
  - period (seconds): Sets the interval time (in seconds) between each attempt to join the network.
  - maximum number of attempts: Sets the maximum number of attempts. If the device fails to join the network after this number of tries, it will stop attempting.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_join_stop.svg">

```python
lora915.join(0)
```

- Stop the device's attempt to join the LoRaWAN network. This block is used when the network joining process is no longer needed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_receive_data.svg">

```python
lora915.receive_data()
```

- Receive downlink data from the buffer. The LoRaWAN network can send data to the device via the downlink, and this block is used to read that data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_send_data.svg">

```python
lora915.send_data('')
```

- Send a data payload to the LoRaWAN network.
  - unconfirm/confirm: Choose whether the sent packet requires confirmation (confirm) or not (unconfirm). Choosing confirmation increases communication reliability but may also increase latency.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_set_join_mode.svg">

```python
lora915.set_join_mode(0)
```

- Set the device's join mode to OTAA (Over The Air Activation), which is the recommended secure method for joining the LoRaWAN network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_915/uiflow_block_lorawan915_set_uplink_app_port.svg">

```python
lora915.set_uplink_app_port(1)
```

- Set the application port for LoRaWAN uplink data. This port is used to identify

 which application the data packet is sent to on the network server.
  - Range: The port number ranges from 1 to 233. Each port number corresponds to a specific application or service, and choosing the correct port ensures that the data is processed correctly.