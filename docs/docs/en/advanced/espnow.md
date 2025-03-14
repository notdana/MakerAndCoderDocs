# ESP-NOW

#>What is ESP-NOW? | ESP-NOW is a short-range, low-power communication protocol that allows multiple devices to communicate without or without using Wi-Fi. This protocol is similar to the low-power 2.4GHz wireless connection commonly seen in wireless mice - devices must be paired before communication. After pairing, the connection between devices is continuous, point-to-point, and does not require a handshake protocol.

## Example

### ESP-NOW Master

The master scans for the AP with the specified SSID to obtain the slave's MAC address, then adds it to the pairing list. In the main loop, it performs data transmission.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_master_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from libs.m5_espnow import M5ESPNOW
import time

setScreenColor(0x222222)

flag_cb = None
slave_mac = None
slave_data = None
run = None
cnt_succes = None
count_send = None
peer_mac = None
slave_ssid = None

now = M5ESPNOW()

title0 = M5Title(title="ESPNOW-MASTER", x=100, fgcolor=0xFFFFFF, bgcolor=0xff0000)
label0 = M5TextBox(24, 75, "SLAVE MAC:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label1 = M5TextBox(125, 38, "label1", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label2 = M5TextBox(24, 109, "SEND COUNT:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label9 = M5TextBox(230, 219, "STOP", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label3 = M5TextBox(126, 75, "label3", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label10 = M5TextBox(24, 175, "REVC COUNT:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label4 = M5TextBox(25, 38, "SLAVE SSID:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label11 = M5TextBox(145, 175, "label11", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label5 = M5TextBox(146, 109, "label5", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label6 = M5TextBox(48, 219, "SEND", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label7 = M5TextBox(24, 144, "SUCCESS COUNT:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label8 = M5TextBox(174, 144, "label8", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)

peer_mac = None

def send_cb(flag):
  global flag_cb,slave_mac,slave_data,run,cnt_succes,count_send,peer_mac,slave_ssid
  flag_cb = flag
  if flag_cb:
    cnt_succes = cnt_succes + 1
    label8.setText(str(cnt_succes))

  pass


def recv_cb(dummy):
  global flag_cb,slave_mac,slave_data,run,cnt_succes,count_send,peer_mac,slave_ssid
  slave_mac, slave_data = now.espnow_recv_str()
  label11.setText(str(slave_data))

  pass

def buttonA_wasPressed():
  global flag_cb, slave_mac, slave_data, run, cnt_succes, count_send, peer_mac, slave_ssid
  run = 1
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonC_wasPressed():
  global flag_cb, slave_mac, slave_data, run, cnt_succes, count_send, peer_mac, slave_ssid
  run = 0
  pass
btnC.wasPressed(buttonC_wasPressed)

now.espnow_init(1, 1)
count_send = 0
cnt_succes = 0
flag_cb = 0
run = 0
slave_ssid = 'M5_Slave'
while peer_mac == None:
  peer_mac = now.espnow_scan(1, slave_ssid)
label1.setText(str(slave_ssid))
label3.setText(str(peer_mac))
now.espnow_add_peer(peer_mac, 1, 0, False)
now.espnow_send_cb(send_cb)
now.espnow_recv_cb(recv_cb)
while True:
  if run:
    count_send = count_send + 1
    now.espnow_send_data(1, str(count_send))
    label5.setText(str(count_send))
    wait_ms(1)
  wait_ms(2)

```

### ESP-NOW Slave

The slave opens an AP hotspot with a specified name (for the master to discover and obtain the MAC address), and in the reception callback, it obtains the sender's MAC address and data, and sends back the same data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_slave_example.svg">


```python
from m5stack import *
from m5ui import *
from uiflow import *
from libs.m5_espnow import M5ESPNOW


setScreenColor(0x222222)
mac_addr = None
data = None
onetime = None
ssid = None

now = M5ESPNOW()

title0 = M5Title(title="ESPNOW-SLAVE", x=105, fgcolor=0xFFFFFF, bgcolor=0xff7c00)
label0 = M5TextBox(26, 82, "MAC ADDR:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label1 = M5TextBox(76, 47, "label1", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label2 = M5TextBox(26, 119, "REMOTE MAC:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label3 = M5TextBox(126, 82, "label3", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label4 = M5TextBox(26, 47, "SSID:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label5 = M5TextBox(150, 119, "label5", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label7 = M5TextBox(26, 159, "REMOTE DATA:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label8 = M5TextBox(157, 159, "label8", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label6 = M5TextBox(26, 195, "SEND DATA:", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)
label9 = M5TextBox(133, 195, "label9", lcd.FONT_Ubuntu, 0xFFFFFF, rotate=0)

def recv_cb(dummy):
  global mac_addr,data,onetime,ssid
  mac_addr, data = now.espnow_recv_str()
  label5.setText(str(mac_addr))
  label8.setText(str(data))
  label9.setText(str(data))
  if onetime:
    now.espnow_add_peer(mac_addr, 1, 1, False)
    now.espnow_recv_cb(recv_cb)
    onetime = 0
  now.espnow_send_data(1, data)

  pass

now.espnow_init(1, 1)
onetime = 1
ssid = 'M5_Slave'
now.espnow_set_ap(ssid, '')
label1.setText(str(ssid))
label3.setText(str(now.espnow_get_mac(0)))
now.espnow_recv_cb(recv_cb)

```


## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_init_channel.svg">

```python
from libs.m5_espnow import M5ESPNOW
now = M5ESPNOW()
now.espnow_init(ch, type)
```

- Initialize ESP-NOW to a specific channel and configure the data type at the same time:
  - ch:0-13
  - type:
    - list: 0
    - string: 1


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_add_peer.svg">

```python
now.espnow_add_peer('', 1, 0, False)
```

- Add a paired device and map it to a specific ID:
  - peer: Device MAC address
  - id:0-10
  - ifidx:s
    - ESP_IF_WIFI_STA:0
    - ESP_IF_WIFI_AP:1
  - encrypt:If encryption is enabled, fill in LMK


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_send_data.svg">

```python
now.espnow_send_data(1, "Hello")
```

- Send data to a device that has been added to the pairing list with a specified ID.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_enable_send_cb.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_send_cb.svg">

```python
def send_cb(flag):
  global flag_cb
  flag_cb = flag
  pass

now.espnow_send_cb(send_cb)
```

- Data send callback:
  - flag: Transmit Status Flag
    - Sent successfully:1
    - Send Failure:0


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_broadcast_data.svg">

```python
now.espnow_broadcast_data('1234')
```

- Broadcast data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_enable_recv_cb.svg">

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_recv_cb.svg">

```python
def recv_cb(dummy):
  slave_mac, slave_data = now.espnow_recv_str()
  print(str(slave_data))
  pass

now.espnow_recv_cb(recv_cb)
```

- Data reception callback

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_get_mac_address.svg">

```python
now.espnow_get_mac(0)
```

- Get local mac address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_get_remote_mac1.svg">

```python
peer_mac = now.espnow_scan(1, slave_ssid)
```

- Scans the specified AP SSID, and obtains its mac address. This feature is commonly used to discover and add new devices. 

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_set_ap_mode1.svg">

```python
now.espnow_set_ap(ssid, '')
```

- Enable the AP hotspot, and specify the SSID and PASSWORD.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_set_pmk.svg">

```python
now.espnow_set_pmk('')
```

- If encrypt is enabled when adding paired devices, both devices can realize encrypted communication by setting the same PMK (Primary Master Key) and encrypting the LMK with AES-128, if not, the default value will be used.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/advanced/espnow/uiflow_block_m5_espnow_deinit.svg">

```python
now.espnow_deinit()
```

- ESP-NOW Deinit


