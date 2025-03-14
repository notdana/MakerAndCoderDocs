# Atom Printer

#>Function Description|The default firmware of Atom Printer will automatically connect to the server after configuring the Wi-Fi connection. Other devices can be controlled remotely by using Atom Printer Block in UIFlow by configuring the same token as the device.


## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/atom_printer/uiflow_block_mqtt_printer_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from MediaTrans.Mqtt_Printer import Mqtt_Printer

setScreenColor(0x222222)
def buttonA_wasPressed():
  # global params
  mqtt.text_print('Hello', 10, 0)
  pass
btnA.wasPressed(buttonA_wasPressed)


mqtt = Mqtt_Printer('94:B9:7E:AC:41:81')
mqtt.start()
```

## API


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/atom_printer/uiflow_block_mqtt_printer_set_topic.svg">

```python
from MediaTrans.Mqtt_Printer import Mqtt_Printer
mqtt = Mqtt_Printer('94:B9:7E:AC:41:81')
mqtt.start()
```

- Setting the Topic (Mac address) of the Atom Printer device


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/atom_printer/uiflow_block_mqtt_printer_print_text.svg">

```python
mqtt.text_print('Hai', 10, 0)
```

- Controls the printing of text messages and sets the location of the print coordinates.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/atom_printer/uiflow_block_mqtt_printer_bar_print.svg">

```python
mqtt.bar_print('1234')
```

- Control Printing BarCode


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/media_trans/atom_printer/uiflow_block_mqtt_printer_qr_print.svg">

```python
mqtt.qr_print('1234')
```

- Control Printing QRCode

