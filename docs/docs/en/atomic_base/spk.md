# Atomic SPK Base

## Example

> This program configures the SD card to play WAV audio files and perform file read/write operations. When button A is pressed, the flag variable `flag` is set to 1, triggering a random number to be written to the file “test.txt.” If the SD card write is successful, the RGB LED turns yellow; otherwise, it turns red. Then, it attempts to read data from the file and play it as an audio frequency. If successful, the RGB LED turns green; otherwise, it turns red. Finally, `flag` resets to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_atomic_base_spk_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.Speaker import Speaker
import time

flag = None
random_num = None
read_data = None

spk = Speaker()

import random

def buttonA_wasPressed():
  global flag, random_num, read_data
  flag = 1
  pass
btnA.wasPressed(buttonA_wasPressed)

flag = 0
spk._tf.init_sdcard(33, 19, 23, 20000000)
spk.playWAV('res/mix.wav', rate=44100, data_format=Speaker.F32B, channel=Speaker.CHN_L, volume=0)
while True:
  random_num = random.randint(100000000, 999999999)
  if flag:
    try :
      with open('/sd/test.txt', 'w+') as fs:
        fs.write(str(random_num))
        rgb.setColorAll(0xffff00)
      pass
    except:
      print('cannot write, please check the sdcard')
      rgb.setColorAll(0xff0000)
    wait_ms(100)
    try :
      with open('/sd/test.txt', 'r+') as fs:
        read_data = fs.read()
        print(read_data)
        spk.playTone(int((int(read_data) / 250000)), 1, volume=0)
        rgb.setColorAll(0x33cc00)
      pass
    except:
      print('cannot read, please check the sdcard')
      rgb.setColorAll(0xff0000)
    flag = 0
  wait_ms(2)

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_init_sdcard.svg">

```python
spk._tf.init_sdcard(33, 19, 23, 20000000)
```

- Initializes the SD card’s SPI communication interface, specifying connections for MISO, MOSI, and SCK pins and setting the communication frequency to 20MHz.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_open_sdcard_file.svg">

```python
with open('/sd/', 'a')
  pass
```

- Opens a file at the specified path in "a" (append) mode.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_cloud_wav.svg">

```python
passspk.playCloudWAV('', volume=0)
```

- Plays a WAV-format audio file from the cloud, with the volume set to 0 (mute).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_sing.svg">

```python
spk.playTone(220, 1, volume=0)
```

- Plays a low A note at a duration of 1 beat, with volume set to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_tone.svg">

```python
spk.playTone(220, 1, volume=0)
```

- Plays a tone at 220Hz frequency, with a duration of 1 beat and volume set to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_wav_dropdown.svg">

```python
/
```

- Plays a local WAV file with volume set to 0 (mute); file is temporarily unspecified.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_wav_file.svg">

```python
spk.playWAV('', volume=0)
```

- Plays a WAV-format audio file from the local directory with volume set to 0.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_play_wav_rate.svg">

```python
spk.playWAV('', rate=44100, data_format=Speaker.F16B, channel=Speaker.CHN_LR, volume=0)
```

- Used to play WAV-format audio files from the SD card or local file system, suitable for playing local music or sound notifications.
    - Play local WAV file: Specifies the path of the local WAV file to play.
    - Sample rate 44100: Sets the audio sample rate to 44100Hz, the standard for CD-quality audio.
    - Data format 16Bit: Specifies a 16-bit data format, a common audio bit depth.
    - Channel left and right: Selects stereo output, using both left and right channels for playback.
    - Volume 0: Sets volume to 0, indicating mute.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_get_seek.svg">

```python
fs.tell()
```

- Retrieves the current file pointer position, indicating the current location in the file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_read.svg">

```python
fs.read(0)
```

- Reads a specified number of bytes from the file (X being the number of bytes to read).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_read_all.svg">

```python
fs.read()
```

- Reads all content from the file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_read_line.svg">

```python
fs.readline()
```

- Reads one line of data from the file, useful for reading text files line by line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_set_seek.svg">

```python
fs.seek(0)
```

- Sets the file pointer’s position, controlling where to start read/write operations in the file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_file_write.svg">

```python
fs.write('')
```

- Writes specified text content to the file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_isdirectory.svg">

```python
spk._tf.is_folder_exist('')
```

- Checks if a folder exists at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_isfile.svg">

```python
spk._tf.is_file_exist('')
```

- Checks if a file exists at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_listdir.svg">

```python
spk._tf.show_directory('')
```

- Displays a list of files and folders in the specified directory,

 showing the directory contents.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_mkdir.svg">

```python
spk._tf.create_folder('')
```

- Creates a new folder at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_remove.svg">

```python
spk._tf.delete_file('')
```

- Deletes a file at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_rename.svg">

```python
spk._tf.rename_file('','')
```

- Renames a file, moving it from an old path to a new path or changing the file name.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/spk/uiflow_block_base_spk_sdcard_rmdir.svg">

```python
spk._tf.delete_folder('')
```

- Deletes a folder at the specified path.