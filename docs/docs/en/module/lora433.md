# Module LoRa433

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

setScreenColor(0x222222)

packet_size = None
check = None

lora433 = module.get(module.LORA433)

def lora433_callback(size):
  global packet_size, check
  packet_size = size
  if packet_size:
    check = lora433.read_packet()
    print(check)
  pass

def buttonA_wasPressed():
  global packet_size, check
  lora433.set_begin_packet()
  lora433.write_packet([0x48, 0x65, 0x6C, 0x6C, 0x6F])
  lora433.set_end_packet()
  pass
btnA.wasPressed(buttonA_wasPressed)

lora433.init_lora_module(cs=5, rst=13, irq=34)
lora433.set_lora_config(freq=433000000, band=125000, TxPow=17, sync=0x34, spreadfactor=7, crate=5, preamble=8, CRC=False)
lora433.set_receive_callback_handler(lora433_callback)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_init.svg">

```python
import module
lora433 = module.get(module.LORA433)
lora433.init_lora_module(cs=5, rst=13, irq=34)
```

- Initialize the LoRa module and specify the relevant CS, RST, IRQ pins


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_config.svg">

```python
lora433.set_lora_config(freq=433000000, band=125000, TxPow=17, sync=0x34, spreadfactor=7, crate=5, preamble=8, CRC=False)
```

- Initialize LoRa configuration:
  - freq:operating frequency
  - band:
    - 7.8 kHz
    - 10.4 kHz
    - 15.6 kHz
    - 20.8kHz
    - 31.25 kHz
    - 41.7 kHz
    - 62.5 kHz
    - 125 kHz
    - 250 kHz
    - 500 kHz
  - TxPow:
    - 0-20dBm
  - sync:synchronized characters
  - spreadfactor:
    - 6-12
  - crate:C/R:
    - C/5-8
  - preamble:preamble length
  - CRC:Whether to enable CRC checking

- Please refer to [sx127x datasheet](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/products/module/Module-LoRa433_V1.1/sx1278.pdf) for detailed configuration parameter meanings and ranges.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_print_msg.svg">

```python
lora433.write_str_packet('')
```

- Send String Data Frame


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_begin_packet.svg">

```python
lora433.set_begin_packet()
```

- Initialize data frame

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_write_buffer.svg">

```python
lora433.write_packet([0x48, 0x65, 0x6C, 0x6C, 0x6F])
```

- Write data to the data frame buffer

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_end_packet.svg">

```python
lora433.set_end_packet()
```

- Finish editing the data frame, and execute the transmission


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_receive_callback.svg">

```python
lora433.set_receive_callback_handler(lora433_callback)
```

- Initialize the receive callback function


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_callback.svg">

```python
def lora433_callback(size):
  global packet_size
  packet_size = size
  pass
```

- Define the receive callback function, the incoming value is the size of the data frame. And through the following data reading, RSSI reading, SNR reading and other related APIs, get the data frame content in the callback.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_message.svg">

```python
lora433.read_str_packet()
```

- Receives data and converts it to a string


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_read.svg">

```python
lora433.read_packet()
```

- Receive raw data Bytearray


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_packet_rssi.svg">

```python
lora433.get_rssi()
```

- Get current data frame RSSI value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_packet_snr.svg">

```python
lora433.get_snr()
```

- Get the current data frame SNR value


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_sleep_mode.svg">

```python
lora433.set_sleep_mode()
```

- Go to sleep mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/lora433/uiflow_block_lora433_stand_by_mode.svg">

```python
lora433.set_standby_mode()
```

- Entering standby mode

