# Module COMX LoRaWAN 470

## Example

#> Use the LoRaWAN 470 module to connect to the network via OTAA mode and periodically send payload data while receiving downlink data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_LoRaWAN470_demo.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from comx.LoRaWAN import LoRaWAN_470
import time

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

flag = None

lora470 = LoRaWAN_470(tx=17, rx=16)
lora470.set_join_mode(0)
lora470.config_OTAA('', '', '')
lora470.set_frequency_band_mask('0400')
lora470.set_rx_window_param(0, 0, 505300000)
lora470.set_class_mode(2)
lora470.set_uplink_downlink_mode(1)
lora470.join(1, 1, 8, 8)
flag = False
while True:
  if not flag and lora470.check_join_status():
    flag = True
    print('Joined')
  if flag:
    lora470.send_data('M5STACK', 1, 5)
    print(lora470.check_downlink_data())
  wait(10)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_check_downlink_data.svg">

```python
lora470.check_downlink_data()
```

- Check and receive downlink data sent from the LoRaWAN gateway to the device. This is used to confirm if data has been transmitted from the server to the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_check_join_status.svg">

```python
lora470.check_join_status()
```

- Check if the device has successfully joined the LoRaWAN network. When the device attempts to connect to the LoRaWAN network, it performs a join operation, and this block checks whether the operation was successful.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_check_sent_status.svg">

```python
lora470.check_uplink_status()
```

- Check the status of uplink data transmission. This is used to confirm whether the data has been successfully transmitted from the device to the LoRaWAN gateway.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_config.svg">

```python
lora470.set_frequency_band_mask('0001')
lora470.set_rx_window_param(0, 0, 505300000)
lora470.set_class_mode(0)
lora470.set_uplink_downlink_mode(1)
```

- Configure the LoRaWAN communication parameters, including the following settings:
  - Frequency band mask: Configure the frequency mask, specifying the frequency range that can be used.
  - RX window param: Set the parameters for the receive window.
  - RX1 offset: Configure the offset for the first receive window.
  - RX2 datarate: Configure the data rate for the second receive window.
  - RX2 freq (Hz): Configure the frequency for the second receive window.
  - Class mode: Set the operating mode of the device, with Class A being a common mode.
  - Uplink downlink mode: Configure the frequency mode for uplink and downlink data, allowing you to choose whether to use the same or different frequencies.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_config_mode.svg">

```python
lora470.config_OTAA('', '', '')
```

- Configure the LoRaWAN device to use OTAA (Over-The-Air Activation) mode for connection. You need to input the device's EUI (Device Identifier), application key (app key), application EUI (Application Identifier), and other information. OTAA mode is a dynamic method for connecting devices through authentication by the network server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_get_abp_config.svg">

```python
lora470.get_ABP_config()
```

- Get the configuration when the device uses ABP (Activation By Personalization) mode. In this mode, the device connects to the network directly using pre-configured session keys without dynamically joining the network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_get_otaa_config.svg">

```python
lora470.get_OTAA_config()
```

- Get the configuration parameters when the device is using OTAA mode. These parameters include the device's EUI, application EUI, application key, etc.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_init.svg">

```python
LoRaWAN_470(tx=0, rx=0)
```

- Initialize the LoRaWAN 470 device's TX (transmit pin) and RX (receive pin). This is used to set the pins for communication between the device and other hardware, ensuring proper data transmission and reception.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_join_start.svg">

```python
lora470.join(1, 1, 8, 1)
```

- Start joining the LoRaWAN network. This block allows you to configure the time interval (in seconds) for the device to automatically join the network and the maximum number of attempts. When "auto join" is enabled, the device will try to join the network at the set time intervals, until successful or until the maximum number of attempts is reached.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_join_stop.svg">

```python
lora470.join(0)
```

- Stop the attempt to join the LoRaWAN network. If the device is trying to join the network, but you want to stop it midway, you can use this block.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_receive_data.svg">

```python
lora470.receive_data()
```

- Receive downlink data from the buffer. This will receive data packets from the LoRaWAN network's downlink (e.g., messages from the server to the device) and process them.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_send_data.svg">

```python
lora470.send_data('')
```

- Send a data payload to the LoRaWAN network. You can choose the confirmation mode for sending data ("unconfirm" means no confirmation required, "confirm" means confirmation is required). This allows the device to send data to the server or other devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_set_join_mode.svg">

```python
lora470.set_join_mode(0)
```

- Set the LoRaWAN device's join mode to OTAA. OTAA (Over-The-Air Activation) is a dynamic device connection method where the network server authenticates the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lorawan_470/uiflow_block_lorawan470_set_uplink_app_port.svg">

```python
lora470.set_uplink_app_port(1)
```

- Set the uplink application port. LoRaWAN communication uses ports to identify different applications or services. This block allows you to set the port number used for uplink data transmission on the device,

 ranging from 1 to 233. This port number is the identifier used in the LoRaWAN network during data transmission to differentiate between different data streams or applications.