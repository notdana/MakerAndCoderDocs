# [Unit CO2](/en/unit/co2)

## Example

Obtain atmospheric CO2 concentration, temperature, humidity and atmospheric pressure data collected by Unit CO2L

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import time
import unit

setScreenColor(0x222222)
co2_0 = unit.get(unit.CO2_SCD40, unit.PORTA)

co2_0.stop_periodic_measurement()
print(co2_0.serial_number())
print(co2_0.get_calibration_enabled())
co2_0.start_periodic_measurement()
wait(1)
while True:
  if co2_0.data_isready():
    co2_0.read_sensor_measurement()
    print((str('data status:') + str((co2_0.data_isready()))))
    print((str('CO2:') + str((co2_0.co2))))
    print((str('Temperature:') + str((co2_0.temperature))))
    wait_ms(25)
  wait_ms(2)
```

## API

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_stop_periodic_measurement.svg" >

```python
co2_0.stop_periodic_measurement()
```

- Stop Periodic Measurements

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_factory_reset.svg
" >

```python
co2_0.factory_reset()
```

- Perform Factory Reset

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_force_calibration.svg" >

```python
co2_0.force_calibration(400)
```

- Force Recalibration of CO2

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_calibration_enabled.svg" >

```python
print(co2_0.get_calibration_enabled())
```

- Get Auto-Calibration Enabled Status

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_data_ready_status.svg" >

```python
print(co2_0.data_isready())
```

- Get Data Ready Status

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_sensor_altitude.svg" >

```python
print(co2_0.get_sensor_altitude())
```

- Get Sensor Height

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_sensor_measurement.svg" >

```python
co2_0.read_sensor_measurement()
```

- Wait for Sensor Measurement Update

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_serial_number.svg" >

```python
print(co2_0.serial_number())
```

- Get Sensor Serial Number

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_get_temperature_offset.svg" >

```python
print(co2_0.get_temperature_offset())
```

- Get Temperature Offset

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_persist_setting.svg" >

```python
co2_0.persist_settings()
```

- Save All Settings to EEPROM

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_power_down.svg" >

```python
co2_0.sleep_mode()
```

- Set Sensor to Sleep Mode

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_read_parameter.svg" >

```python
print(co2_0.co2)
```

- Get CO2/Humidity/Temperature Values

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_reinit.svg" >

```python
co2_0.reinit()
```

- Reinitialize Sensor

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_self_test.svg" >

```python
co2_0.self_test()
```

- Perform Self-Test

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_set_ambient_pressure.svg" >

```python
co2_0.set_ambient_pressure(0)
```

- Set Ambient Air Pressure

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_set_auto_calibration.svg" >

```python
co2_0.set_calibration_enabled(1)
```

- Set Auto-Calibration Enabled

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_set_sensor_altitude.svg" >

```python
co2_0.set_sensor_altitude(0)
```

- Set Sensor Height from Ground (Mark)

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_set_temperature_offset.svg" >

```python
co2_0.set_temperature_offset(4)
```

- Set Temperature Offset

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_start_low_periodic_measurement.svg" >

```python
co2_0.start_low_periodic_measurement()
```

- Start Low Frequency Measurements (30 Seconds Interval)

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_start_periodic_measurement.svg" >

```python
co2_0.start_periodic_measurement()
```

- Start Device Measurements

<img  class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/co2/uiflow_block_unit_co2_wake_up.svg" >

```python
co2_0.wake_up()
```

- Wake Up Sensor
