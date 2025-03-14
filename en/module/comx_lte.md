# Module COMX LTE

## Example

### HTTP GET

#> Initialize the TX and RX pins for the LTE module.<br>Print the module status, signal quality, network registration status, and GPRS network registration status.<br>In the main loop, check the GPRS network registration status, and if registration is successful, execute an HTTP GET request to access [http://www.m2msupport.net/m2msupport/test.php](http://www.m2msupport.net/m2msupport/test.php), retrieve data from the response, and print the results.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_com_lte_demo.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from comx.lte import LTE

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

resp = None

lte = LTE(tx=13, rx=5)
print(lte.check_status())
print(lte.get_single_quality())
print(lte.get_network_registration())
print(lte.get_gprs_network_registration())
while True:
  if str((lte.get_gprs_network_registration())) == '1':
    # echo "test"
    resp = lte.http_get('http://www.m2msupport.net/m2msupport/test.php')
    if resp:
      print(resp[1])
  wait_ms(2)

```

### HTTP POST

#> Initialize the TX and RX pins for the LTE module.<br>Print the module status, signal quality, network registration status, and GPRS network registration status.<br>In the main loop, check the GPRS network registration status, and if registration is successful, create a dictionary containing a random integer, convert it to JSON format, and send it via an HTTP POST request to `http://httpbin.org/post`, then parse the response, extract the data, and print the results.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_com_lte_demo_post.svg">

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
from comx.lte import LTE
import json

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

resp = None
post_data = None

import random

lte = LTE(tx=13, rx=5)
print(lte.check_status())
print(lte.get_single_quality())
print(lte.get_network_registration())
print(lte.get_gprs_network_registration())
while True:
  if str((lte.get_gprs_network_registration())) == '1':
    post_data = {'random1':random.randint(0, 100)}
    resp = lte.http_post('http://httpbin.org/post', 'application/json', str((json.dumps(post_data))))
    if resp:
      print((json.loads(resp[1]))['data'])
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_check_gprs_network_registration.svg">

```python
lte.get_gprs_network_registration()
```

- Checks whether the device is registered to the GPRS network. This is typically used to determine if the device has successfully connected to the GPRS network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_check_network_registration.svg">

```python
lte.get_network_registration()
```

- Checks whether the device is registered to a mobile network. This is used to verify if the device is connected to any available mobile network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_check_single_quality.svg">

```python
lte.get_single_quality()
```

- Checks the quality of the current network signal. Returns a value representing signal strength, which is crucial for assessing the stability of the network connection.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_check_status.svg">

```python
lte.check_status()
```

- Checks the status of the module. This command is used to get the operating status of the device, such as whether it is functioning correctly and if there are any errors.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_enable_pdp_context.svg">

```python
lte.enable_PDP_context()
```

- Enables PDP (Packet Data Protocol) context. This is a necessary step for activating a data connection, allowing the device to send and receive data over the mobile network.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_http_get.svg">

```python
lte.http_get('')
```

- Initiates an HTTP(S) GET request to retrieve data from the specified URL. Commonly used to fetch information from a server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_http_post.svg">

```python
lte.http_post('', 'application/json', '')
```

- Initiates an HTTP(S) POST request to send data to the specified URL. The data can be in JSON format or other types, used for uploading data to a server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_http_terminate.svg">

```python
lte.http_terminate()
```

- Terminates the current HTTP(S) connection. Used to close an established HTTP(S) connection to free up resources or end a session.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_init.svg">

```python
LTE(tx=13, rx=5)
```

- Initializes the LTE module by setting the serial TX and RX pins. This operation prepares the LTE module for communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_power_down_module.svg">

```python
lte.poweroff()
```

- Powers off the module. This puts the module into low-power mode or completely shuts it down to save power.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_reset_module.svg">

```python
lte.reset()
```

- Resets the module, causing it to restart and return to its initial state. This is used to clear faults or reconfigure the module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/comx_lte/uiflow_block_comlte_set_echo_mode.svg">

```python
lte.set_command_echo_mode(0)
```

- Sets the command echo mode. Selecting OFF will disable command echoing, meaning the module will no longer echo back received AT commands. This is typically used to reduce redundancy in communication.