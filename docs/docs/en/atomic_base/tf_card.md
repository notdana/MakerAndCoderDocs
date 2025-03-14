# Atomic TF Card Base

> This program uses the SD card for file and folder creation, deletion, renaming, and reading/writing operations. The main steps are as follows:
1. Configure SD card pins and delete the `m5test.txt` file and `m5 folder` folder (if they exist).
2. Create and write a text file `m5.txt` with content “welcome to M5,” then read and print the file content.
3. Check if the `m5test.txt` file exists and print the check result.
4. Rename `m5.txt` to `m5test.txt` and check its existence again.
5. Create `m5test.txt` within `m5 folder` and append “hello to M5,” then read and print all content. Base

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_atomic_base_tfcard_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
from base.TF_Card import TFCARD

tf = TFCARD()

tf.init_sdcard(33, 19, 23, 20000000)
tf.delete_file('m5test.txt')
tf.delete_folder('m5 folder')
with open('/sd/m5.txt', 'w+') as fs:
  fs.write('welcome to M5')
with open('/sd/m5.txt', 'r+') as fs:
  print(fs.read())
print(tf.show_directory(''))
if tf.is_file_exist('m5test.txt'):
  print('file is exist')
else:
  print('file is not exist')
tf.rename_file('m5.txt','m5test.txt')
tf.create_folder('m5 folder')
print(tf.show_directory(''))
if tf.is_file_exist('m5test.txt'):
  print('file is exist')
else:
  print('file is not exist')
with open('/sd/m5test.txt', 'a') as fs:
  fs.write('hello to M5')
with open('/sd/m5test.txt', 'r+') as fs:
  print(fs.read())
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_init_sdcard.svg">

```python
tf.init_sdcard(33, 19, 23, 20000000)
```

- Initializes the SD card interface configuration, specifying MISO, MOSI, SCK pins, and operating frequency. This operation is used to set up SD card communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_get_seek.svg">

```python
fs.tell()
```

- Retrieves the current file reading position (seek). This is used to keep track of the file pointer position during file operations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_read.svg">

```python
fs.read(0)
```

- Reads a specified number of bytes from the file. This command reads file content, and the number of bytes to read can be set in the parameter.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_read_all.svg">

```python
fs.read()
```

- Reads all content from the file. This block is used to read the entire content of a file at once, ideal for handling smaller files.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_read_line.svg">

```python
fs.readline()
```

- Reads one line of content from the file. This is used for line-by-line processing of data in text files.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_set_seek.svg">

```python
fs.seek(0)
```

- Sets the reading position in the file. This can move the file pointer to a specific location within the file to perform read or write operations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_file_write.svg">

```python
fs.write('')
```

- Writes text to a file. This command writes the specified text content to the file, typically used to record or save data to the SD card.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_isdirectory.svg">

```python
tf.is_folder_exist('')
```

- Checks if a folder exists at the specified path. Returns true if the folder exists, otherwise returns false.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_isfile.svg">

```python
tf.is_file_exist('')
```

- Checks if a file exists at the specified path. Returns a similar result as the folder existence check.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_listdir.svg">

```python
tf.show_directory('')
```

- Displays the list of files and folders at the specified path. This operation lists the contents of a directory, allowing users to view stored files and folders.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_mkdir.svg">

```python
tf.create_folder('')
```

- Creates a new folder at the specified path. If the path is valid and permissions allow, a new folder will be created in the specified location.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_open_tfcard_file.svg">

```python
with open('/sd/', 'a')
```

- Opens a file at the specified path with the set mode (e.g., read, write, etc.). Different modes control how the file is opened (e.g., read, write, append).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_remove.svg">

```python
tf.delete_file('')
```

- Deletes a file at the specified path. This block removes a file from the storage medium.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_rename.svg">

```python
tf.rename_file('','')
```

- Renames a file from the old path to the new path. By providing the old and new paths, you can rename a file.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/atomic_base/tf_card/uiflow_block_base_tfcard_rmdir.svg">

```python
tf.delete_folder('')
```

- Deletes a folder at the specified path. When given the folder path, the system will remove that folder and its contents (if non-empty folders are allowed to be deleted).