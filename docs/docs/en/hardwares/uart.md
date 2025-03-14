# UART

## Example

Continuously exchange data between `uart1` and `uart2` to achieve bidirectional communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_demo.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *

setScreenColor(0x292929)

label0 = M5TextBox(15, 106, "Slave Baud", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label1 = M5TextBox(12, 130, "115200", lcd.FONT_DejaVu40, 0x02c7fc, rotate=0)
label2 = M5TextBox(15, 20, "TX", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label3 = M5TextBox(139, 20, "RX", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label4 = M5TextBox(12, 40, "G17", lcd.FONT_DejaVu40, 0x00ff38, rotate=0)
label5 = M5TextBox(136, 40, "G16", lcd.FONT_DejaVu40, 0x00ff38, rotate=0)
label9 = M5TextBox(173, 106, "/", lcd.FONT_DejaVu72, 0xFFFFFF, rotate=0)
label10 = M5TextBox(199, 125, "PC default baud", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label11 = M5TextBox(224, 149, "115200", lcd.FONT_Default, 0xFFFFFF, rotate=0)

uart1 = machine.UART(1, tx=1, rx=3)
uart1.init(115200, bits=8, parity=None, stop=1)
uart2 = machine.UART(2, tx=17, rx=16)
uart2.init(115200, bits=8, parity=None, stop=1)
while True:
  if uart1.any():
    uart2.write(bytes(uart1.read()))
  if uart2.any():
    uart1.write(bytes(uart2.read()))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart.svg"> 

```python
uart1 = machine.UART(1, tx=14, rx=13)
uart1.init(9600, bits=8, parity=None, stop=1)
```

- Sets the TX and RX pins and configures the communication parameters (baud rate, data bits, parity, and stop bits) for serial communication.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_write_line.svg"> 

```python
uart1.write('' + "\r\n")
```
 
- Sends a string via `uart1`, followed by a carriage return and newline to signify the end of the line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_write.svg"> 

```python
uart1.write('')
```

- Sends a string via `uart1`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_write_raw_data.svg"> 

```python
uart1.write(bytes([0, 0, 0]))
```

- Sends an array containing three byte values via `UART1`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_read.svg"> 

```python
str(uart1.read())
```

- Reads the data received by `UART1` and converts it to a string.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_read_characters.svg"> 

```python
label0.set_text(str(uart1.read(10)))
```

- Reads up to 10 bytes of data received by `UART1`, converts it to a string, and sets it as the text of `label0`.
  - "10": Sets the maximum number of bytes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_readline.svg"> 

```python
str(uart1.readline())
```

- Reads a line of data received by `UART1` and converts it to a string.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/uart/uiflow_block_uart_any.svg"> 

```python
str(uart1.any())
```

- Checks if there is data available to read in the `UART1` receive buffer and converts the result to a string.