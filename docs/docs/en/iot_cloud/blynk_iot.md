# Blynk IoT

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from IoTcloud import blynk2
import time
import unit

setScreenColor(0x222222)
env3_0 = unit.get(unit.ENV3, unit.PORTA)

V_value = None
V_pins = None
Hum = None
Tmp = None
stat = None

blynk2_1 = blynk2.Blynk('WoW6dPeQ5lHCQgG6wahvYHF7WyrG6bde')

label0 = M5TextBox(38, 34, "Temp:", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label1 = M5TextBox(38, 77, "Hum:", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label2 = M5TextBox(38, 119, "Slider1:", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label4 = M5TextBox(144, 34, "label4", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label5 = M5TextBox(144, 77, "label5", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label6 = M5TextBox(144, 119, "label6", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label7 = M5TextBox(144, 158, "label7", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label3 = M5TextBox(38, 158, "Pins:", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label8 = M5TextBox(144, 185, "label8", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)
label9 = M5TextBox(144, 210, "label9", lcd.FONT_DejaVu18, 0xFFFFFF, rotate=0)

@blynk2_0.on("V*")
def blynk2_0_read_handler_vpins(pin, value):
  global V_value, V_pins, Hum, Tmp, stat
  V_value = value[0]
  V_pins = pin
  label6.setText(str(V_value))
  label7.setText(str(V_pins))

  pass

def buttonB_wasPressed():
  global V_value, V_pins, Hum, Tmp, stat
  blynk2_0.connect()
  pass
btnB.wasPressed(buttonB_wasPressed)

while True:
  stat=blynk2_0.state
  Hum = env3_0.humidity
  Tmp = env3_0.temperature
  blynk2_0.virtual_write(3, Tmp)
  blynk2_0.virtual_write(4, Hum)
  label4.setText(str(Tmp))
  label5.setText(str(Hum))
  label8.setText(str(stat))
  blynk2_0.run()
  wait_ms(100)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_init.svg">

```python
from IoTcloud import blynk2
blynk2_0 = blynk2.Blynk('')
```

- Initialize client connection information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_init_server.svg">

```python
from IoTcloud import blynk2
blynk2_1 = blynk2.Blynk('', insecure=False, server='', port=443, heartbeat=5)
```

- Initialize client, and configure Blynk server address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_connect.svg">

```python
blynk2_0.connect()
```

- Start client connect


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_get_state.svg">

```python
print(blynk2_0.state)
```

- Get server connection status:
  - Disconnect:0
  - Connecting:1
  - Connected:2


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_disconnect.svg">

```python
blynk2_0.disconnect()
```

- Disconnect client connection.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_run.svg">

```python
blynk2_0.run()
```

- Client status update, needs to be placed in the main loop.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_set_virtual_write.svg">

```python
blynk2_0.virtual_write(0, '')
```

- Write data to virtual pin.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_set_sync_virtual.svg">

```python
blynk2_0.sync_virtual(0)
```

- Synchronize virtual pin status.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_event_read_pin.svg">

```python
@blynk2_1.on("V0")
def blynk2_1_v0_read_handler(value):
  V0_value = value[0]
  pass

```

- Virtual pin read event callback function.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/iot_cloud/blynk_iot/uiflow_block_iot_blynk2_event_read.svg">

```python
@blynk2_0.on("V*")
def blynk2_0_read_handler_vpins(pin, value):
  V_value = value[0]
  V_pins = pin
  pass
```

- Universal virtual pin read event callback function.


