# Math

## Example

Simple logical operations and variable assignment

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_example.svg" >

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_number.svg" >

```python
date = 10
```

- Add a constant

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_arithmetic.svg" >

```python
date = 11 + 12
```

- Perform `addition`/`subtraction`/`multiplication`/`division`/`modulus`/`exponentiation` operations on both sides of the equation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_arithmetic_arr.svg" >

```python
date = 13 + 4 - 8 % 2 - 7
```

- Perform `addition`/`subtraction`/`multiplication`/`division`/`modulus`/`exponentiation` operations on two or more values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_bit_operation.svg" >

```python
date = 5 & 6
```

- Bitwise operation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_constant.svg" >

```python
date = math.pi
```

- Assign the constant value of π

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_modulo.svg" >

```python
date = 9 % 2
```

- Modulus operation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_number_property.svg" >

```python
date = 8 % 2 == 0
```

- Detect a data value. `even`/`old`/`prime`/`whole`/`positive`/`negative`/`divisible by`

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_on_list.svg" >

```python
date = sum(list1)
```

- Array operation function

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_random_float.svg" >

```python
date = random.random()
```

- Output a random floating-point number between 0 and 1

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_random_int.svg" >

```python
date = random.randint(0, 10)
```

- Output a random number within a specific range

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_constrain.svg" >

```python
date = min(max(50, 1), 100)
```

- Limit the range of a data value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_remap.svg" >

```python
date = math.remap(0, 0, 1023, 0, 255)
```

- Value mapping

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_round.svg" >

```python
date = round(2.4)
```

- Round a number using the round() function

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_single.svg" >

```python
date = math.sqrt(0)
```

- Apply mathematical functions to a numeric value. `sqrt()`/`log()`/`log10()`/`exp()`/`pow()`

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_trig.svg" >

```python
date = math.sin(10 / 180.0 * math.pi)
```

- Trigonometric functions. `sin()`/`cos()`/`tan()`/`asin()`/`acos()`/`atan()`

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_convent_int.svg" >

```python
date = int('8')
```

- Convert the data type to int

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_convent_float.svg" >

```python
date = float('0.8')
```

- Convert the data type to float

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_clear_bit.svg" >

```python
date = ((10 >> 0) & 0x01)
```

- Clear a specific bit in a data value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_get_bit.svg" >

```python
date = (10 | (0x01 << 0))
```

- Get a specific bit in a data value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_set_bit.svg" >

```python
date = (10 & (~ (0x01 << 0)))
```

- Modify a specific bit in a data value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_int_from_bytes.svg" >

```python
date = int.from_bytes(10, 'big')
```

- Flip the least significant bit of a given value

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/generic/math/uiflow_block_math_reverse_bit.svg" >

```python
date = (10 ^ (0x01 << 0))
```

- Convert a byte sequence to an integer
