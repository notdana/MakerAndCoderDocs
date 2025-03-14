# Atom Socket

## Example

> This program remotely controls the device via the MQTT protocol, monitoring the load’s voltage, current, and power, and starts a web server in AP mode to poll data. When button A is pressed, the relay state toggles (on/off), and the RGB LED color updates to indicate the status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atomic_base_socket_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.Socket_Kit import Socket
import time

button_next = None

sock = Socket()

from numbers import Number

def buttonA_wasPressed():
  global button_next
  button_next = (button_next if isinstance(button_next, Number) else 0) + 1
  if button_next == 1:
    sock.set_relay_state(1)
  elif button_next == 2:
    sock.set_relay_state(0)
    button_next = 0
  pass
btnA.wasPressed(buttonA_wasPressed)

button_next = 0
sock.remote_control(1)
print(sock.pub_topic)
print((str('This is Subscribe Topic(Relay State), Use Remote User: ') + str((sock.sub_topic_relay))))
print((str('This is Subscribe Topic(Parameter Status), Use Remote User: ') + str((sock.sub_topic_data))))
while True:
  if sock.wait_update_data():
    print((str('Voltage(V): ') + str((sock.get_voltage()))))
    print((str('Current(mA): ') + str((sock.get_current()))))
    print((str('Power(W): ') + str((sock.get_active_power()))))
    sock.server_loop()
    wait(1)
  button_next = int((sock.get_relay_status()))
  if button_next:
    rgb.setColorAll(0x009900)
  else:
    rgb.setColorAll(0xff0000)
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_get_publish_topic.svg">

```python
sock.pub_topic
```

- Retrieves the device’s data publishing topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_get_subscribe_topic.svg">

```python
sock.sub_topic_relay
```

- Retrieves the subscription topic for the device, which receives messages published to this topic.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_load_active_power.svg">

```python
sock.get_active_power()
```

- Gets the current active power of the device’s load.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_load_current.svg">

```python
sock.get_current()
```

- Retrieves the current load current of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_load_voltage.svg">

```python
sock.get_voltage()
```

- Retrieves the current load voltage of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_relay_status.svg">

```python
sock.get_relay_status()
```

- Gets the current state (on/off) of the relay.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_remote_control.svg">

```python
sock.remote_control(1)
```

- Sets the device to remote control mode, here configured for MQTT.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_server_loop.svg">

```python
sock.server_loop()
```

- Enables a web server polling loop when the device is in AP mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_set_relay_state.svg">

```python
sock.set_relay_state(1)
```

- Sets the relay state to "on".

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/socket/uiflow_block_atom_socket_kit_wait_update_data.svg">

```python
sock.wait_update_data()
```

- Waits for the device to receive and process updated data.