# [Unit NCIR2](/en/unit/ncir2)

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
ncir2_0 = unit.get(unit.NCIR2, unit.PORTA)

ncir2_0.init_i2c_address(0x5A)
while True:
  print((str('temperature:') + str((ncir2_0.temperature_measure()))))
  print((str('emissivity:') + str((ncir2_0.emissivity_measure()))))
  print((str('threshold value:') + str((ncir2_0.temperature_threshold(0x20)))))
  print((str('buzzer frequency:') + str((ncir2_0.temp_buzzer_freq(0x40)))))
  wait(1)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_init.svg">

```python
ncir2_0.init_i2c_address(0x5A)
```

- Initialize I2C communication address

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_button_status.svg">

```python
print(ncir2_0.button_status())
```

- Retrieve button state (pressed or released)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_buzzer_control.svg">

```python
print(ncir2_0.buzzer_control())
```

- Retrieve buzzer enable status (on or off)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_buzzer_duty.svg">

```python
print(ncir2_0.buzzer_duty())
```

- Retrieve buzzer duty cycle (duty cycle value 0-255, higher value indicates louder sound)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_buzzer_freq.svg">

```python
print(ncir2_0.buzzer_freq())
```

- Retrieve buzzer frequency value (default 4000 Hz)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_device_status.svg">

```python
print(ncir2_0.read_device_status(0xFE))
```

- Retrieve device firmware version or I2C address (default I2C address is 0x5A)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_device_temp.svg">

```python
print(ncir2_0.chip_temperature_measure())
```

- Retrieve device temperature value (in ℃)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_emissivity.svg">

```python
print(ncir2_0.emissivity_measure())
```

- Retrieve reflectance of an object's surface

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_rgb_led.svg">

```python
print(ncir2_0.rgb_led())
```

- Retrieve RGB LED color (RGB values range from 0-255)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temperature.svg">

```python
print(ncir2_0.temperature_measure())
```

- Retrieve temperature value (redundant, but assuming it's for clarity)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temp_buzzer_duty.svg">

```python
print(ncir2_0.temp_buzzer_duty(0x44))
```

- Set buzzer duty cycle at maximum and minimum temperature thresholds (duty cycle value 0-255, higher value indicates louder sound)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temp_buzzer_freq.svg">

```python
print(ncir2_0.temp_buzzer_freq(0x40))
```

- Retrieve buzzer frequency at maximum or minimum temperature thresholds (default 4000 Hz, higher value indicates sharper sound)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temp_buzzer_interval.svg">

```python
print(ncir2_0.temp_alarm_interval(0x42))
```

- Retrieve buzzer high-low level intervals at maximum or minimum temperature thresholds (default low: 100, high: 204)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temp_led_color.svg">

```python
print(ncir2_0.temp_alarm_led(0x30))
```

- Retrieve LED color at maximum or minimum temperature thresholds (RGB values range from 0-255)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_get_temp_threshold.svg">

```python
print(ncir2_0.temperature_threshold(0x20))
```

- Retrieve maximum and minimum temperature thresholds (default set to minimum 10°C, maximum 37°C)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_save_setting.svg">

```python
ncir2_0.save_config_setting()
```

- Save current configuration settings

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_buzzer_duty.svg">

```python
ncir2_0.buzzer_duty(80)
```

- Retrieve buzzer duty cycle (duty cycle value 0-255, higher value indicates louder sound) (redundant, but for completeness)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_buzzer_freq.svg">

```python
ncir2_0.buzzer_freq(4000)
```

- Set buzzer frequency (default 4000 Hz, higher value indicates louder sound, but note: frequency does not directly correlate to loudness, it affects pitch)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_control.svg">

```python
ncir2_0.buzzer_control(0x01)
```

- Set buzzer enable status (on or off)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_emissivity.svg">

```python
ncir2_0.emissivity_measure(0.95)
```

- Set reflectance (skin reflectance is 0.95)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_i2c_address.svg">

```python
ncir2_0.write_i2c_address(0x5A)
```

- Set device's I2C address (default 0x5A)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_rgb_led.svg">

```python
ncir2_0.rgb_led(50, 50, 50)
```

- Set RGB LED color values (RGB values range from 0-255)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_temp_buzzer_duty.svg">

```python
ncir2_0.temp_buzzer_duty(0x44, 80)
```

- Set buzzer duty cycle at maximum and minimum temperature thresholds (duty cycle value 0-255, higher value indicates louder sound) (redundant, but for consistency)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_temp_buzzer_freq.svg">

```python
ncir2_0.temp_buzzer_freq(0x40, 4000)
```

- Set buzzer intervals at maximum or minimum temperature thresholds (higher value indicates faster response)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_temp_buzzer_interval.svg">

```python
ncir2_0.temp_alarm_interval(0x42, 100)
```

- (Duplicate entry) Set buzzer intervals at maximum or minimum temperature thresholds (higher value indicates faster response)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_temp_led_color.svg">

```python
ncir2_0.temp_alarm_led(0x30, 50, 50, 50)
```

- Set buzzer frequency at maximum or minimum temperature thresholds (default 4000 Hz, higher value indicates sharper sound)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/ncir2/uiflow_block_unit_ncir2_set_temp_threshold.svg">

```python
ncir2_0.temperature_threshold(0x20, 25)
```

- Set LED RGB color values at maximum or minimum temperature thresholds (RGB values range from 0-255)

