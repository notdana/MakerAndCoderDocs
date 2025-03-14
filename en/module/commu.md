# Module COMMU

## Example

#> Initialize CAN, I2C, and RS485 communication modules, then in a loop, read and process data based on interrupts and data status. Generate random data and send it via CAN and RS485, while scanning and checking the status of I2C devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_commu_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module
import time

setScreenColor(0x3a3a3a)
rand = None
temp_data = None

com = module.get(module.COMMU)

import random

com.commu_can_init(3, 15)
i2c = com.commu_i2c_init(21, 22, 0x44, 100000)
rs485 = com.commu_uart_init(2, 17, 16, 115200, 8, None, 1)
print((str('I2C Device:') + str((i2c.scan()))))
while True:
  if com.commu_can_interrupt_occur():
    print((str('CAN Message:') + str((com.commu_can_read_message(1)))))
    print((str('CAN ID:') + str((com.commu_can_id))))
  if i2c.available():
    print('TRUE')
    print((str('I2C Device:') + str((i2c.scan()))))
  else:
    print('FALSE')
  if rs485.any():
    print((str('RS485 Data:') + str((rs485.read()).decode())))
  rand = random.randint(10000000, 16777215)
  wait(1)
  temp_data = [(rand & 0xff0000) >> 16, (rand & 0x00ff00) >> 8, rand & 0xff]
  com.commu_can_send_message(0x100, temp_data)
  print((str('temp data:') + str(temp_data)))
  wait(1)
  rs485.write(str(rand))
  print((str('rand data:') + str(rand)))
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_available_msg.svg">

```python
com.commu_can_available_message()
```

- Check if there is an available message on the CAN bus. If there is, it returns True; otherwise, it returns False. This is typically used to determine whether new data needs to be read.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_clear_interrupt.svg">

```python
com.commu_can_clear_interrupts()
```

- Clear the interrupt flags of the CAN module. This is usually used to reset the interrupt status so that the CAN module can continue processing new interrupts or messages.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_config_rate.svg">

```python
com.commu_can_config_rate(15)
```

- Configure the communication rate of the CAN bus. You can choose different rates (e.g., 500 KBPS) to match your network settings. This is important for ensuring the stability and compatibility of the communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_debug.svg">

```python
com.commu_can_debug(True)
```

- Enable or disable debug information output for the CAN module. When enabled, debug information will be printed, which is usually used for diagnosing and troubleshooting CAN communication issues.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_init.svg">

```python
com.commu_can_init(3, 15)
```

- Initialize the CAN module, setting the operating mode and communication rate. You can choose different modes (e.g., ANY mode) and rates (e.g., 500 KBPS) to suit different application needs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_interrupt_occur.svg">

```python
com.commu_can_interrupt_occur()
```

- Check whether an interrupt has occurred on the interrupt pin of the CAN module. If an interrupt occurs, it returns True; otherwise, it returns False. This block is used to detect the occurrence of interrupt events so that they can be handled when necessary.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_read_msg.svg">

```python
com.commu_can_read_message(1)
```

- Read a message from the CAN bus. You can choose the type of message to read (e.g., LIST) to obtain the data currently being transmitted on the bus. This is a key step in receiving data from the CAN bus.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_remote_id.svg">

```python
com.commu_can_id
```

- Send a remote frame request to request data from a device with a specific CAN ID. This is useful when you need to retrieve specific information from other nodes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_reset.svg">

```python
com.commu_can_reset()
```

- Reset the CAN module, returning it to its initial state. This is usually done to clear errors or reinitialize the CAN module to ensure proper operation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_send_msg.svg">

```python
com.commu_can_send_message(0x100, [0, 0, 0])
```

- Send a data message with a specific CAN ID to the CAN bus. You can define a data list to determine the content of the data being sent. This is the primary method for communicating between devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_can_set_mode.svg">

```python
com.commu_can_set_mode(0x00)
```

- Set the CAN module to "NORMAL" mode. This means the CAN module will normally participate in communication on the bus, rather than being in silent or receive-only mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_available.svg">

```python
i2c.available()
```

- Check the available addresses on the I2C bus and return them as a list. This block helps detect devices connected to the I2C bus.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_get_data_in_list.svg">

```python
[][0]
```

- Get data from the index position in a list. In this example, it retrieves data from index 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_init.svg">

```python
com.commu_i2c_init(21, 22, 0x50, 100000)
```

- Initialize the I2C bus by defining the pins for the data line (SDA) and clock line (SCL), the device address (0x50), and the communication frequency (100,000 Hz). This block is used to set the parameters for I2C communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_read_data.svg">

```python
i2c.read_data(0, i2c_bus.UINT8LE)
```

- Read data from the I2C device. You can specify the amount of data to read (num) and the data type (UINT8LE indicates an unsigned 8-bit little-endian data).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_read_mem_data.svg">

```python
i2c.read_mem_data(0, 0, i2c_bus.UINT8LE)
```

- Read a specified amount of data (num) from a specific register (reg) of the I2C device, with the data type UINT8LE. This block is typically used to read data from a specific register of a device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_read_reg.svg">

```python
i2c.read_reg(0x00, 0)
```

- Read a specified number of bytes from register 0x00. In this example, it attempts to read 0 bytes of data. This is typically used for reading small amounts of data from an I2C device's register.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_read_req.svg">

```python
i2c.read_u8(0x00)
```

- Read one byte of data from register 0x00. This block directly reads a single byte of information, useful for reading single-byte register values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_read_res.svg">

```python
i2c.read_u16(0x00, byteorder="big")
```

- Read a short data (two bytes) from register 0x00 and decode it in big-endian format (big). Big-endian decoding means the high byte is first.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_scan.svg">

```python
i2c.scan()
```

- Scan all devices connected to the I2C bus and return the detected device addresses. This block is used to check whether devices are connected and communicating on the I2C bus.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_write_big.svg">

```python
i2c.write_u16(0x00, 0x0000, byteorder="big")
```

- Write a short data (two bytes) 0x0000 to register 0x00, encoding it in big-endian format (big). Big-endian encoding means the high byte is written first.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_write_byte.svg">

```python
i2c.write_u8(0x00, 0x00)
```

- Write a byte 0x00 to register 0x00. This block is used to write a single byte of data to a specific register.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_write_data.svg">

```python
i2c.write_data(0, i2c_bus.UINT8LE)
```

- Write the specified data 0 of type UINT8LE (8-bit unsigned integer, little-endian format) to the device. This is typically used to write general data without specifying a register address.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_write_mem_data.svg">

```python
i2c.write_mem_data(0, 0, i2c_bus.UINT8LE)
```

- Write data 0 to register 0, with data type UINT8LE (8-bit unsigned integer, little-endian format). This block is used to write specific types of data to a specified register.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_i2c_write_mem_list.svg">

```python
i2c.write_mem_list(0, [0, 0, 0])
```

- Write a list of bytes (here [0, 0, 0]) to register 0. This block is used to write multiple bytes of data to a specified register at once.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_any.svg">

```python
uart.any()
```

- This block is used to check whether there is any remaining data in the buffer of the UART interface. It is typically used to handle continuous data transmission, ensuring that all buffered data is read or processed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_init.svg">

```python
com.commu_uart_init(1, 1, 3, 9600, 8, None, 1)
```

- Initialize the UART port (port number 1) using the specified configuration for serial communication. In this configuration: TX pin is 1, RX pin is 3, baud rate is 9600, 8 data bits, no parity, and 1 stop bit.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_read.svg">

```python
uart.read()
```

- Read all available data from the UART interface. This block is typically used to receive complete data frames or read a continuous data stream.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_readline.svg">

```python
uart.readline()
```

- Read a line of data from the UART interface until a newline character is encountered. This is typically used to read serially transmitted data line by line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_read_characters.svg">

```python
uart.read(0)
```

- Read a specified number of bytes from the UART interface. In this example, 0 bytes of data are read; in actual use, you should set the number of bytes to read.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_write.svg">

```python
uart.write('')
```

- Send the specified string data via the UART interface. This block is used to send text or commands to serial devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_write_line.svg">

```python
uart.write(''+"\r\n")
```

- Write the specified string data as a line to the UART interface, automatically appending a newline character at the end. This is typically used to send a line of text data, similar to the println function.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/commu/uiflow_block_module_commu_uart_write_raw_data.svg">

```python
uart.write(bytes([0, 0, 0]))
```

- This block is used to send a list of raw data via the UART interface. You can create a list containing multiple bytes and then send these byte data through the UART. This is typically used in applications where binary data or data in a specific format needs to be sent.