
# Socket

## UDP Server

### Example

Create a UDP Server to listen for data reception, and send back the same data content. Through the network-related APIs can get the current IP address of the local machine, used to provide other Client data sending.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_example.svg"> 


```python
from m5stack import *
from m5ui import *
from uiflow import *
import network
import socket

setScreenColor(0x222222)
wlan = network.WLAN(network.STA_IF)
wlan.active(True)
wlan.connect('SSID', 'PASSWORD')
print(wlan.ifconfig())

udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.bind(('0.0.0.0', 5000))
while True:
  print(udpsocket.recv(1024))
  wait_ms(2)
```


### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_start.svg"> 

```python
udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.bind(('0.0.0.0', 5000))
```

- Create a socket server and specify the IP (usually 0.0.0.0 is used to listen locally) and the port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_sendto.svg"> 

```python
udpsocket.sendto('Hello', ('192.168.31.11', 5000))
```

- Send data to the specified IP and port

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_close.svg"> 

```python
udpsocket.close()
```

- Close the socket.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_recv.svg"> 

```python
data = udpsocket.recv(1024)
```

- Block the receiving of listening data, set the maximum buffer length, and return when data is received.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_server_read.svg"> 

```python
data = udpsocket.read(10)
```

- Block the receiving of listening data, and set the length of the receiving buffer, and return when the receiving buffer is full.

## UDP Client

### Example

Create a UDP Client to send data to the specified server.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *
import socket
import time
setScreenColor(0x222222)

udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.connect(('192.168.31.10', 5000))
while True:
  udpsocket.send('Hello World')
  wait(1)
  wait_ms(2)
```


### API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_start.svg"> 

```python
udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.connect(('192.168.31.10', 5000))
```

- Create a socket server and specify the destination IP and port to send data to.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_sendmsg.svg"> 

```python
udpsocket.send('Hello World')
```

- Send character data


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_sendto.svg"> 

```python
udpsocket.write('')
```

- Write raw data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_sendto.svg"> 

```python
udpsocket.sendto('Hello World', ('192.168.31.10', 5000))
```

- Send data to the specified IP and port

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_close.svg"> 

```python
udpsocket.close()
```

- Close the socket.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_recv.svg"> 

```python
data = udpsocket.recv(1024)
```

- Block the receiving of listening data, set the maximum buffer length, and return when data is received.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/socket/uiflow_block_socket_udp_client_read.svg"> 

```python
data = udpsocket.read(10)
```

- Block the receiving of listening data, and set the length of the receiving buffer, and return when the receiving buffer is full.

