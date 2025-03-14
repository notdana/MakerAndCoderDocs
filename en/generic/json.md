# Json

## Example

JSON is a lightweight data interchange format, and here's how to use JSON functions


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *
from libs.json_py import *
import json

date = None

date = py_2_json({'author':'M5Stack','people':100,'device':'CoreS3','number':5})
print(json.dumps(date))
print(get_json_keys(date))
print(get_json_key(date, 'number'))
print(get_json_values(date))
print(get_json_keys_len(date))
set_json_elements(date, 'people', 101)
set_json_elements(date, 'devicetow', 'core2')
delete_json_elements(date, 'number')
print(json.dumps(date))
print(json.loads('{"string":"stack","number":100}'))
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_dumps_json.svg"> 

```python
print(json.dumps(date))
```

- Convert (serialize) a Python object (such as a list or dictionary) into a JSON-formatted string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_add_key_value.svg"> 

```python
set_json_elements(date, 'devicetow', 'core2')
```

- Add a key-value pair to a JSON object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_create.svg"> 

```python
date = py_2_json({'author':'M5Stack','people':100,'device':'CoreS3','number':5})
```

- Create a JSON object using key-value pairs

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_del_key.svg"> 

```python
delete_json_elements(date, 'number')
```

- Delete a key-value pair from a JSON object based on the key

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_get_key_value.svg"> 

```python
print(get_json_key(date, 'number'))
```

- Get the value of a specified key from a JSON object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_get_keys.svg"> 

```python
print(get_json_keys(date))
```

- Get all keys from a JSON object and return them as a list

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_get_keys_len.svg"> 

```python
print(get_json_keys_len(date))
```

- Get the length of a JSON object (note: for dictionaries, it's the number of key-value pairs)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_get_values.svg"> 

```python
print(get_json_values(date))
```

- Get all values from a JSON object and return them as a list

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_json_set_key_value.svg"> 

```python
set_json_elements(date, 'people', 101)
```

- Set the value of a corresponding key in a JSON object

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/JSON/uiflow_block_variables_set.svg"> 

```python
print(json.loads('{"string":"stack","number":100}'))
```

- Parse a string containing a valid JSON object
