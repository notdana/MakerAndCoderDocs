# Atomic GPS Base

## Example

> Retrieves and prints time, latitude, longitude, and altitude data to the serial port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_atomic_base_gps_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.GPS import GPS
import time

gps.deinit()
while True:
  print(gps.timestamp)
  print(gps.latitude)
  print(gps.longitude)
  print(gps.altitude)
  wait(2)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_deinit.svg">

```python
gps.deinit()
```

- Deinitializes the GPS module, releasing resources.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_init.svg">

```python
gps = GPS(0, '')
```

- Initializes the GPS module and sets the timezone.
  - `timezone` specifies the time offset.
  - `formatting` specifies the time format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_init_sdcard.svg">

```python
gps._tf.init_sdcard(33, 19, 23, 20000000)
```

- Configures the SD card communication pins and SPI frequency, specifying MISO (Pin 33), MOSI (Pin 19), SCK (Pin 23), and frequency (20000000Hz).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_altitude.svg">

```python
gps.altitude
```

- Retrieves altitude data from the GPS module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_course.svg">

```python
gps.course
```

- Retrieves the current course (direction of travel) from the GPS module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_date.svg">

```python
gps.date
```

- Retrieves the current date from the GPS module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_geoid_height.svg">

```python
gps.geoid_height
```

- Retrieves the geoid height at the current position.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_hdop.svg">

```python
gps.hdop
```

- Retrieves the horizontal dilution of precision (HDOP), representing GPS positioning accuracy.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_last_sv_sentence.svg">

```python
gps.last_sv_sentence
```

- Retrieves the last received satellite visibility (SV) sentence, typically used for debugging GPS signal.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_latitude.svg">

```python
gps.latitude
```

- Retrieves the current latitude value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_longitude.svg">

```python
gps.longitude
```

- Retrieves the current longitude value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_open_sdcard_file.svg">

```python
with open('/sd/', 'a')
  pass
```

- Opens a file on the SD card in the specified mode. `path` specifies the file path, `mode` specifies the mode (e.g., read, write, append).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_pdop.svg">

```python
passprint(gps.pdop)
```

- Retrieves the position dilution of precision (PDOP), indicating positioning accuracy.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_satellites_in_use.svg">

```python
gps.satellites_in_use
```

- Retrieves the number of satellites currently in use for positioning.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_satellites_in_view.svg">

```python
gps.satellites_in_view
```

- Retrieves the number of satellites currently in view, representing all detected satellites.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_satellites_used.svg">

```python
gps.satellites_used
```

- Retrieves the number of satellites actually used for positioning.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_satellite_data.svg">

```python
gps.satellite_data
```

- Retrieves current satellite data from the GPS module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_get_seek.svg">

```python
fs.tell()
```

- Retrieves the current position of the read pointer in a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_read.svg">

```python
fs.read(0)
```

- Reads a specified number of bytes from a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_read_all.svg">

```python
fs.read()
```

- Reads all content from a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_read_line.svg">

```python
fs.readline()
```

- Reads one line of data from a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_set_seek.svg">

```python
fs.seek(0)
```

- Sets the file read pointer position.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_file_write.svg">

```python
fs.write('')
```

- Writes specified text to a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_isdirectory.svg">

```python
gps._tf.is_folder_exist('')
```

- Checks if a folder exists at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_isfile.svg">

```python
gps._tf.is_file_exist('')
```

- Checks if a file exists at the specified path.

<img class="blockly_svg" src="https

://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_listdir.svg">

```python
gps._tf.show_directory('')
```

- Displays the list of files and folders at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_mkdir.svg">

```python
gps._tf.create_folder('')
```

- Creates a new folder at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_remove.svg">

```python
gps._tf.delete_file('')
```

- Deletes a file at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_rename.svg">

```python
gps._tf.rename_file('', '')
```

- Renames a file from the old path to a new path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_sdcard_rmdir.svg">

```python
gps._tf.delete_folder('')
```

- Deletes a folder at the specified path.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_speed.svg">

```python
gps.speed
```

- Retrieves current speed data from the GPS module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_timestamp.svg">

```python
gps.timestamp
```

- Retrieves the current timestamp, typically acquired from satellite signals.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_total_sv_sentence.svg">

```python
gps.total_sv_sentence
```

- Retrieves the total count of satellite visibility (SV) sentences.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/gps/uiflow_block_base_gps_vdop.svg">

```python
gps.vdop
```

- Retrieves the vertical dilution of precision (VDOP), indicating vertical positioning accuracy.