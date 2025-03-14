# Repeat

## Example

Loop function usage

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *

date = None
list2 = None
i = None
j = None

date = 10
list2 = [5, 6, 7]
for count in range(10):
  date = date + 1
while date < 25:
  date = date * 2
for i in list2:
  date = date + i
for j in range(0, 6, 2):
  date = date + 1
  if j == 3:
    break
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_controls_repeat.svg">

```python
for count in range(10):
  date = date + 1
```

- Customize the number of times to run the content of the do block

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_controls_forEach.svg">

```python
list2 = [5, 6, 7]
for i in list2:
  date = date + i
```

- Iterate through the contents of an array sequentially, assigning each value to the variable i, and executing the content of the do block once for each iteration

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_controls_whileUntil.svg">

```python
while date < 25:
  date = date * 2
```

- Perform a series of operations in a loop until a condition is no longer satisfied

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_controls_for.svg">

```python
for j in range(0, 6, 2):
  date = date + 1
  if j == 3:
    break
```

- Increment from a to b, with each increment being c, and assign each incremented result to the variable i. For each iteration, execute the content of the do block once

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/loops/uiflow_block_controls_flow_statements.svg">

```python
break
```

