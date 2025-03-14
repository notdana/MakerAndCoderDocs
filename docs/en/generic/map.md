# Map

## Example 

map function is a common built-in function or method in many programming languages. It is mainly used for iterable objects. Here is how to use map function

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *

date = None

date = {'a':1,'b':2,'c':'3'}
print('a' in date.keys())
print(date['b'])
date['d'] = '4'
date['a'] = '11'
date.pop('b')
date.clear()
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_set_map_key.svg">

```python
date['a'] = '11'
```

- Set key-value pairs in a dictionary

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_get_map_in.svg">

```python
print('a' in date.keys())
```

- Check if a key exists

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_add_map_key.svg">

```python
date['d'] = '4'
```

- Add a key-value pair to a dictionary

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_delete_map_key.svg">

```python
date.pop('b')
```

- Delete a specified key

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_get_map_key.svg">

```python
print(date['b'])
```

- Retrieve the value of a key

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_map_clear.svg">

```python
date.clear()
```

- Clear the dictionary

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Map/uiflow_block_map_on_loop.svg">

```python
date = {'a':1,'b':2,'c':'3'}
```

- Establish key-value pairs
