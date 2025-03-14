# [Unit CO2L](/en/unit/CO2L)

## Example

Obtain atmospheric CO2L concentration, temperature, humidity and atmospheric pressure data collected by Unit CO2L

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
co2l_0 = unit.get(unit.CO2_SCD41, unit.PORTA)

co2l_0.start_periodic_measurement()
while True:
  print(co2l_0.co2)
  print(co2l_0.data_isready())
  print(co2l_0.get_temperature_offset())
  print(co2l_0.get_sensor_altitude())
  print(co2l_0.serial_number())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_stop_periodic_measurement.svg" >

```python
co2l_0.stop_periodic_measurement()
```

- Stop Periodic Measurements

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_factory_reset.svg
">

```python
co2l_0.factory_reset()
```

- Perform Factory Reset

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_force_calibration.svg" >

```python
co2l_0.force_calibration(400)
```

- Force Recalibration of CO2

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_calibration_enabled.svg" >

```python
print(co2l_0.get_calibration_enabled())
```

- Get Auto-Calibration Enabled Status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_data_ready_status.svg" >

```python
print(co2l_0.data_isready())
```

- Get Data Ready Status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_sensor_altitude.svg" >

```python
print(co2l_0.get_sensor_altitude())
```

- Get Sensor Height

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_sensor_measurement.svg" >

```python
co2l_0.read_sensor_measurement()
```

- Wait for Sensor Measurement Update

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_serial_number.svg" >

```python
print(co2l_0.serial_number())
```

- Get Sensor Serial Number

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_get_temperature_offset.svg" >

```python
print(co2l_0.get_temperature_offset())
```

- Get Temperature Offset

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_persist_setting.svg" >

```python
co2l_0.persist_settings()
```

- Save All Settings to EEPROM

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_power_down.svg" >

```python
co2l_0.sleep_mode()
```

- Set Sensor to Sleep Mode

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_read_parameter.svg" >

```python
print(co2l_0.co2)
```

- Get CO2/Humidity/Temperature Values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_reinit.svg" >

```python
co2l_0.reinit()
```

- Reinitialize Sensor

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_self_test.svg" >

```python
co2l_0.self_test()
```

- Perform Self-Test

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_set_ambient_pressure.svg" >

```python
co2l_0.set_ambient_pressure(0)
```

- Set Ambient Air Pressure

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_set_auto_calibration.svg" >

```python
co2l_0.set_calibration_enabled(1)
```

- Set Auto-Calibration Enabled

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_set_sensor_altitude.svg" >

```python
co2l_0.set_sensor_altitude(0)
```

- Set Sensor Height from Ground (Mark)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_set_temperature_offset.svg" >

```python
co2l_0.set_temperature_offset(4)
```

- Set Temperature Offset

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_single_shot_measurement_all.svg
" >

```python
co2l_0.single_shot_measurement_all()
```

- All single measurements (low power mode) (5s to obtain a value)

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_single_shot_measurement_ht.svg" >

```python
co2l_0.single_shot_measurement_ht()
```

- Single measurement of humidity and temperature

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_start_low_periodic_measurement.svg" >

```python
co2l_0.start_low_periodic_measurement()
```

- Set Temperature Offset

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_start_periodic_measurement.svg" >

```python
co2l_0.start_periodic_measurement()
```

- Start Device Measurements

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2l/uiflow_block_unit_co2l_wake_up.svg" >

```python
co2l_0.wake_up()
```

- Wake Up Sensor
