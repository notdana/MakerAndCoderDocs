# SPI


## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_init.svg"> 

```python
spi2 = machine.SPI(1, 500000, sck=machine.Pin(-1), miso=machine.Pin(-1), mosi=machine.Pin(-1), firstbit=machine.SPI.MSB, polarity=0, phase=0)
```

- Initialize the SPI interface, set the baud rate, pins, and other communication parameters.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_deinit.svg"> 

```python
spi2.deinit()
```
 
- Deinitialize the SPI interface, stop its operation, and release related resources.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_write.svg"> 

```python
spi2.write(buf)
```

- Send data from the buffer `buf` through the SPI interface.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_write_readinto.svg"> 

```python
spi2.write_readinto(write_buf, read_buf)
```

- Send data from `write_buf` through the SPI interface and simultaneously receive data into `read_buf`.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_read.svg"> 

```python
str(spi2.read(0))
```

- Read the specified number of bytes from the SPI interface and convert the result to a string.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/spi/uiflow_block_spi_write_readinto.svg"> 

```python
spi2.readinto(buf)
```

- Read data from the SPI interface and store it into the buffer `buf`.