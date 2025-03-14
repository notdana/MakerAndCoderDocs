# [Unit GPS](/en/unit/gps)

## Example

Get local time, latitude and longitude information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
gps_0 = unit.get(unit.GPS, unit.PORTC)

while True:
  print(gps_0.gps_time)
  print(gps_0.latitude)
  print(gps_0.longitude)
  print(gps_0.pos_quality)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_uart_init.svg">

```python
gps_0.uart_port_id(1)
```

- Set ID parameter

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_altitude.svg">

```python
print(gps_0.altitude)
```

- Get altitude

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_course.svg">

```python
print(gps_0.course)
```

- Get road information

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_date.svg">

```python
print(gps_0.gps_date)
```

- Get GPS data

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_latitude.svg">

```python
print(gps_0.latitude)
```

- Get latitude (string format: dddmm.mmmmm)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_latitude_decimal.svg">

```python
print(gps_0.latitude_decimal)
```

- Get latitude (string format: dd.ddd)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_longitude.svg">

```python
print(gps_0.longitude_decimal)
```

- Get longitude (string format: dddmm.mmmmm)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_longitude_decimal.svg">

```python
print(gps_0.longitude)
```

- Get longitude (float format: dd.ddd)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_positioning_quality.svg">

```python
print(gps_0.pos_quality)
```

- Get positioning accuracy

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_satellite_num.svg">

```python
print(gps_0.satellite_num)
```

- Get number of satellites in view

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_speed.svg">

```python
print(gps_0.speed_knot)
```

- Get ground speed

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_get_state.svg">

```python
print(gps_0.gps_time)
```

- Get local time

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/gps/uiflow_block_unit_gps_set_time_zone.svg">

```python
gps_0.set_time_zone(0)
```

- Set local timezone
