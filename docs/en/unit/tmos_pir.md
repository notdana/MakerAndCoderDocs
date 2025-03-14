# [Unit TMOS PIR](/en/unit/UNIT-TMOS%20PIR)

## Example

> Continuously update and print TMOS PIR sensor data in the main loop, including motion state, presence state, ambient temperature changes, and object temperature.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/uiflow_block_unit_tmos_pir_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

tmos_0 = unit.get(unit.TMOS, unit.PORTA)

while True:
  tmos_0.tick_callback()
  print(tmos_0.get_data_ready())
  print(tmos_0.get_motion_state())
  print(tmos_0.get_motion_value())
  print(tmos_0.get_presence_state())
  print(tmos_0.get_presence_value())
  print(tmos_0.get_tamb_shock_state())
  print(tmos_0.get_tambient_raw_value())
  print(tmos_0.get_temperature_data())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/1_uiflow_block_unit_tmos_get_data_ready.svg">

```python
tmos_0.get_data_ready()
```

- Checks if the sensor data has been updated. Returns True if the latest sensor readings are available; otherwise, returns False.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/2_uiflow_block_unit_tmos_get_motion_state.svg">

```python
tmos_0.get_motion_state()
```

- Checks if motion has been detected. Returns True if the sensor has detected motion; otherwise, returns False.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/3_uiflow_block_unit_tmos_get_motion_value.svg">

```python
tmos_0.get_motion_value()
```

- Retrieves the motion detection value. This may indicate the intensity or range of detected motion, typically returned as an integer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/4_uiflow_block_unit_tmos_get_presence_state.svg">

```python
tmos_0.get_presence_state()
```

- Checks if presence (i.e., a person in the area) has been detected. Returns True if presence is detected; otherwise, returns False.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/5_uiflow_block_unit_tmos_get_presence_value.svg">

```python
tmos_0.get_presence_value()
```

- Retrieves the presence detection value, similar to the motion detection value, but used to determine if someone is within the sensor's range.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/6_uiflow_block_unit_tmos_get_tamb_shock_state.svg">

```python
tmos_0.get_tamb_shock_state()
```

- Checks if a sudden change in ambient temperature has been detected. Returns True if a significant temperature change is detected; otherwise, returns False.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/7_uiflow_block_unit_tmos_get_tambient_raw_value.svg">

```python
tmos_0.get_tambient_raw_value()
```

- Reads the current ambient temperature, typically returned as an integer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/8_uiflow_block_unit_tmos_get_temperature_data.svg">

```python
tmos_0.get_temperature_data()
```

- Reads the temperature of an object in front of the sensor, returned as a floating-point number.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/9_uiflow_block_unit_tmos_callback.svg">

```python
def tmos_0_ambient_temperature_shock_detect_event(arg):
  # global params
  pass
tmos_0.set_callback(tmos_0_ambient_temperature_shock_detect_event, tmos_0.AMBIENT_TEMPERATURE_SHOCK_DETECT)
```

- Triggers an event when the sensor detects ambient temperature changes. This block can be set to perform actions under certain conditions, such as temperature variations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/10_uiflow_block_unit_tmos_tick.svg">

```python
tmos_0.tick_callback()
```

- Repeatedly executed operation in the program's main loop. This can be used to regularly check the sensor's state or read values.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/11_uiflow_block_unit_tmos_get_gain_mode.svg">

```python
tmos_0.get_gain_mode()
```

- Retrieves the sensor's gain mode. The gain mode determines how the sensor processes signals, typically represented as an integer.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/12_uiflow_block_unit_tmos_get_tmos_sensitivity.svg">

```python
tmos_0.get_tmos_sensitivity()
```

- Retrieves the sensor's sensitivity. This is a floating-point number, with higher values indicating greater sensitivity.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/13_uiflow_block_unit_tmos_get_motion_threshold.svg">

```python
tmos_0.get_motion_threshold()
```

- Retrieves the threshold for motion detection. This is an integer value; a lower value may mean even slight movements will be detected.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/14_uiflow_block_unit_tmos_get_motion_hysteresis.svg">

```python
tmos_0.get_motion_hysteresis()
```

- Retrieves the motion detection hysteresis value, which defines the stability that must be reached before the sensor stops reporting motion.


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/15_uiflow_block_unit_tmos_get_presence_threshold.svg">

```python
tmos_0.get_presence_threshold()
```

- Retrieves the threshold for presence detection. Setting this value adjusts when a presence is considered detected.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/16_uiflow_block_unit_tmos_get_presence_hysteresis.svg">

```python
tmos_0.get_presence_hysteresis()
```

- Retrieves the presence detection hysteresis value, which determines the stability period before the presence reporting stops.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/17_uiflow_block_unit_tmos_get_tambient_shock_threshold.svg">

```python
tmos_0.get_tambient_shock_threshold()
```

- Retrieves the threshold for detecting rapid changes in ambient temperature. This threshold is used to trigger events for significant temperature changes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/18_uiflow_block_unit_tmos_get_tambient_shock_hysteresis.svg">

```python
tmos_0.get_tambient_shock_hysteresis()
```

- Retrieves the hysteresis value for detecting rapid changes in ambient temperature. This setting helps prevent false alerts due to minor temperature fluctuations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/19_uiflow_block_unit_tmos_set_gain_mode.svg">

```python
tmos_0.set_gain_mode(0)
```
- Sets the sensor's gain mode to wide gain mode. This mode may offer a broader detection range or greater signal amplification.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/20_uiflow_block_unit_tmos_set_tmos_sensitivity.svg">

```python
tmos_0.set_tmos_sensitivity(0)
```

- Sets the sensor's sensitivity. This value can be adjusted from 0 to 4080, with higher values indicating increased sensitivity.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/21_uiflow_block_unit_tmos_set_motion_threshold.svg">

```python
tmos_0.set_motion_threshold(200)
```

- Sets the threshold for motion detection. This value determines how much movement is recognized as valid motion, adjustable from 0 to 32767.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/22_uiflow_block_unit_tmos_set_motion_hysteresis.svg">

```python
tmos_0.set_motion_hysteresis(0)
```

- Sets the motion detection hysteresis value. This value helps prevent the sensor from frequently switching states under borderline conditions, adjustable from 0 to 255.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/23_uiflow_block_unit_tmos_set_presence_threshold.svg">

```python
tmos_0.set_presence_threshold(200)
```

- Sets the threshold for presence detection. Similar to the motion threshold, this setting determines what level of "presence" is considered valid, also adjustable from 0 to 32767.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/24_uiflow_block_unit_tmos_set_presence_hysteresis.svg">

```python
tmos_0.set_presence_hysteresis(0)
```

- Sets the presence detection hysteresis value. This value stabilizes the sensor's output, preventing frequent changes due to minor variations.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/25_uiflow_block_unit_tmos_set_tambient_shock_threshold.svg">

```python
tmos_0.set_tambient_shock_threshold(200)
```

- Sets the threshold for detecting rapid changes in ambient temperature. This value determines what speed of temperature change is considered significant.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/toms_pir/26_uiflow_block_unit_tmos_set_tambient_shock_hysteresis.svg">

```python
tmos_0.set_tambient_shock_hysteresis(0)
```

- Sets the hysteresis value for detecting rapid changes in ambient temperature. This setting helps prevent false alarms due to slight temperature fluctuations.