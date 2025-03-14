# Module GPS

## Example

#> Serial print the device's longitude and latitude

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

screen = M5Screen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

gps = module.get(module.GPS, (17, 16))

while True:
  print((str('Latitude: ') + str((gps.latitude))))
  print((str(' Longitude: ') + str((gps.longitude))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_altitude.svg">

```python
gps.altitude
```

- Get altitude in meters, returns a string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_course.svg">

```python
gps.course
```

- Get course information, returns a string. The course refers to the direction relative to the Earth's North Pole

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_date.svg">

```python
gps.gps_date
```

- Get date information, returns a string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_latitude.svg">

```python
gps.latitude
```

- Get latitude information, returns a string. The format is degrees and minutes (ddmm.mmmmm) and includes the east/west (W/E) designation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_latitude_decimal.svg">

```python
gps.latitude_decimal
```

- Get latitude in decimal format, returns a float

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_longitude.svg">

```python
gps.longitude
```

- Get longitude information, returns a string. The format is degrees and minutes (dddmm.mmmmm) and includes the north/south (S/N) designation

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_longitude_decimal.svg">

```python
gps.longitude_decimal
```

- Get longitude in decimal format, returns a float

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_positioning_quality.svg">

```python
gps.pos_quality
```

- Get positioning quality, returns a string. Typically used to indicate the quality or accuracy of the GPS signal

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_satellite_num.svg">

```python
gps.satellite_num
```

- Get the number of satellites connected, returns a string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_speed.svg">

```python
gps.speed_knot
```

- Get speed, returns a string. The speed can be in:
  - Knot: A unit of speed commonly used in maritime and aviation.
  - Kph: Kilometers per hour, commonly used in land transportation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_get_state.svg">

```python
gps.gps_time
```

- Get current time, returns a string

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_set_custom.svg">

```python
module.get(module.GPS, (17, 16))
```

- Initialize with custom pins, TX pin is 17 and RX pin is 16. This is used to set custom serial communication pins

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_set_time_zone.svg">

```python
gps.set_time_zone(8)
```

- Set the time zone, the range is -12 to 12. In this example, the time zone is set to 8

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/gps/uiflow_block_gps_uart_init.svg">

```python
gps.uart_port_id(1)
```

- Set the core UART ID number. This is used to specify the UART interface to be used
  - 1: Set the core UART ID number to 1.
  - 2: Set the core UART ID number to 2.