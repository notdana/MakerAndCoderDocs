# Functions

## Example

Define two functions that take parameters for simple arithmetic operations

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Functions/uiflow_block_example.svg"> 

```python
from m5stack import *
from m5ui import *
from uiflow import *

x = None
y = None
result = None

# Describe this function...
def func(x, y):
  global result
  if x < y:
    print(x + y)
  else:
    print(x - y)

# Describe this function...
def mathfuc(y, x):
  global result
  if x < 0:
    return y - x
  return x + y

func(2, 3)
result = mathfuc(10, 5)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Functions/uiflow_block_procedures_defnoreturn.svg"> 

```python
def func(x, y):
  global result
  if x < y:
    print(x + y)
  else:
    print(x - y)
```

- Create a function that can be configured with parameters and the function does not return a value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Functions/uiflow_block_procedures_defreturn.svg"> 

```python
def mathfuc(y, x):
  global result
  return x + y
```

- Create a function that can be configured with parameters and the function does return a value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/Functions/uiflow_block_procedures_ifreturn.svg"> 

```python
if x < 0:
    return y - x
```

- Perform a simple if logic operation within the function, end the function operation, and return a value
