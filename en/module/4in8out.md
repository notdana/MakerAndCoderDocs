# Module13.2 4In8Out

## Example

#>Print out the firmware version, control the output channel on and off, and read the input channel status


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_4in8out_demo4.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x222222)
i = None
module_4in8out = module.get(module.MODULE_4IN8OUT)

module_4in8out.init_i2c_address(0x45)
print((str('Module Firmware Version:') + str((module_4in8out.read_status(0XFE)))))
while True:
  for i in range(8):
    module_4in8out.write_output_pin(i, 1)
  wait(1)
  for i in range(8):
    module_4in8out.write_output_pin(i, 0)
  wait(1)
  for i in range(4):
    print((str('CH') + str(((str(i) + str(((str(' Input :') + str((module_4in8out.read_input_pin(i)))))))))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_module_4in8out_init.svg">

```python
module_4in8out.init_i2c_address(0x45)
```

- Initializes the I2C address of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_module_4in8out_read_pin.svg">

```python
module_4in8out.read_input_pin(0)
```

- Retrieves the status or value of the input channel.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_module_4in8out_read_status.svg">

```python
module_4in8out.read_status(0XFE)
```

- Retrieves the status information of the device, selecting to get the firmware version (FW_VERSION).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_module_4in8out_set_address.svg">

```python
module_4in8out.set_i2c_address(0x45)
```

- Sets the I2C address of the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/4in8out/uiflow_block_module_4in8out_write_pin.svg">

```python
module_4in8out.write_output_pin(0, 1)
```

- Controls the status of the output channel. This example sets the output status of channel 0, with options to set it to "ON" or "OFF." This is used to control devices or circuits connected to the channel, such as turning a relay or LED on or off.

## Video

<TabPanel>
  <template #tab-Bilibili>
      <div class="video-iframe">
        <iframe src="//player.bilibili.com/player.html?isOutside=true&aid=113580544361157&bvid=BV1yA6PYZEZQ&cid=27134460306&p=1&autoplay=0" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
      </div>
  </template>
  <template #tab-Youtube>
      <div class="video-iframe">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/g28O_zxvCm0?si=UlJ9RH5BKMrTwTe6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
      </div>
  </template>
</TabPanel>