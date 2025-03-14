# RTC

## Example

Set different time zones and display the real-time clock on the serial monitor (year, month, day, hour, minute, second, weekday).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_demo1.svg"> 

```python
from m5stack import *
from m5stack_ui import *
from uiflow import *
import time

rtc.settime('ntp', host='cn.pool.ntp.org', tzone=8)
while True:
  print(rtc.datetime()[0])
  print(rtc.datetime()[1])
  print(rtc.datetime()[2])
  print(rtc.datetime()[3])
  print(rtc.datetime()[4])
  print(rtc.datetime()[5])
  print(rtc.datetime()[6])
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_set_time_ntp_host_and_timezone.svg"> 

```python
rtc.settime('ntp', host='cn.pool.ntp.org', tzone=8)
```

- Set the time through the NTP (Network Time Protocol) host server and adjust according to the time zone. You can choose the following NTP servers:

- **cn.pool.ntp.org**: China NTP server
- **jp.pool.ntp.org**: Japan NTP server
- **sg.pool.ntp.org**: Singapore NTP server
- **tw.pool.ntp.org**: Taiwan NTP server
- **hk.pool.ntp.org**: Hong Kong NTP server
- **us.pool.ntp.org**: United States NTP server
- **de.pool.ntp.org**: Germany NTP server

#> Synchronize with the NTP server `cn.pool.ntp.org` to set the time and adjust according to the +8 hour time zone offset.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_year.svg"> 

```python
str(rtc.datetime()[0])
```
 
- Get the current date and time, and use index [0] to extract the year, then convert it to string format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_month.svg"> 

```python
str(rtc.datetime()[1])
```

- Get the current date and time, and use index [1] to extract the month, then convert it to string format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_date.svg"> 

```python
str(rtc.datetime()[2])
```

- Get the current date and time, and use index [2] to extract the date, then convert it to string format.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_week.svg"> 

```python
str(rtc.datetime()[3])
```

- Get the current date and time, and use index [3] to extract the weekday, then convert it to string format.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_hour.svg"> 

```python
str(rtc.datetime()[4])
```

- Get the current date and time, and use index [4] to extract the hour, then convert it to string format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_minute.svg"> 

```python
str(rtc.datetime()[5])
```

- Get the current date and time, and use index [5] to extract the minute, then convert it to string format.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_second.svg"> 

```python
str(rtc.datetime()[6])
```

- Get the current date and time, and use index [6] to extract the second, then convert it to string format.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_set_time.svg"> 

```python
rtc.datetime((0, 1, 1, 0, 0, 0, 0, 0))
```

- Set the date and time with parameters (year, month, day, weekday, hour, minute, second, millisecond).


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_get_real_time.svg"> 

```python
str(rtc.datetime())
```

- Get the current RTC (real-time clock) time and convert it to string format.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/hardwares/rtc/uiflow_block_rtc_print_real_time.svg"> 

```python
str(rtc.printRTCtime())
```

- Return the current RTC time and convert it to string format.