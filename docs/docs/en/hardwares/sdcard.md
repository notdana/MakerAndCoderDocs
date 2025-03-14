# SDCard

## Example

- SDCard file read and write operations

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *
from hardware import sdcard
setScreenColor(0x222222)

sdcard.SDCard(20000000)
with open('/sd/test.txt', 'w+') as fs:
  fs.write('Hello World')
with open('/sd/test.txt', 'r') as fs:
  print(fs.read())

```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_init_clock.svg"> 


```python
sdcard.SDCard(20000000)
```

- Setting the SDCard bus clock frequency


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_open.svg"> 


```python
with open('/sd/test.txt', 'w+') as fs:
    pass

```

- Opens the specified file and performs read or write operations inside it. r and r+ modes must exist or an error will occur. a, w, and w+ modes automatically create the file if it does not exist.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_write.svg"> 


```python
fs.write('Hello World')
```

- Write to file


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_seek.svg"> 


```python
fs.seek(0)
```

- Manipulate the file cursor movement position


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_mkdir.svg"> 


```python
fs.seek(0)
```

- Creating Folders

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_remove.svg"> 


```python
os.remove('/sd/filename')
```

- Deleting a file with a specified path


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_rmdir.svg"> 


```python
os.rmdir('/sd/folder')
```

- Delete a specified path folder


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_rename.svg"> 


```python
os.rename('/sd/old', '/sd/new')
```

- Renaming of documents

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_read_all.svg"> 


```python
fs.read()
```

- Read all data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_read_bytes.svg"> 


```python
fs.read(1024)
```

- Read data of specified length

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_read_line.svg"> 


```python
fs.readline()
```

- Read a line of data


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_get_seek.svg"> 


```python
fs.tell()
```

- Read the current file cursor position


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_listdir.svg"> 


```python
os.listdir('/sd/')
```

- Viewing Catalog Files

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_is_file.svg"> 


```python
os.stat('/sd/')[0] == 0x8000
```

- Check if the path is a file

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_is_directory.svg"> 


```python
os.stat('/sd/')[0] == 0x4000
```

- Check if the path is a directory


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/sdcard/uiflow_block_sd_file_exist.svg"> 


```python
'' in os.listdir('/sd/')
```

- Check if a file is included in the path

