# variables

## Example

Create variable

```python
from m5stack import *
from m5ui import *
from uiflow import *

date = None

from numbers import Number

date = 10
date = (date if isinstance(date, Number) else 0) + (0 + 1)
print(date)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/variables/uiflow_block_variables_set.svg">

```python
date = 10
```

- Assign values to variables

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/variables/uiflow_block_math_change.svg">

```python
date = (date if isinstance(date, Number) else 0) + (0 + 1)
```

- Modify the current variable, the input parameter is the modified size (e.g. +10, -10), can be an expression. If the variable value is not of type number, the result of the input parameter is assigned to the current variable.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/variables/uiflow_block_variables_get.svg">

- Perform value assignment
