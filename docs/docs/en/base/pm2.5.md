# PM2.5

## Example

### PM2.5(SHT20 Version)

#> Obtain the values of pm2.5 particles and sht20 temperature and humidity values

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_sht20_Demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

setScreenColor(0x222222)

pm25_sht20 = module.get(module.PM25)

while True:
  print((str('SPM PM1.0:') + str((pm25_sht20.get_pm1_0_factory()))))
  print((str('SPM PM2.5:') + str((pm25_sht20.get_pm2_5_factory()))))
  print((str('SPM PM10:') + str((pm25_sht20.get_pm10_factory()))))
  print((str('ATE PM1.0:') + str((pm25_sht20.get_pm1_0_air()))))
  print((str('ATE PM2.5:') + str((pm25_sht20.get_pm2_5_air()))))
  print((str('ATE PM10:') + str((pm25_sht20.get_pm10_air()))))
  print((str('>3.0um Particles:') + str((pm25_sht20.get_num_above_0_3()))))
  print((str('TEM:') + str((pm25_sht20.get_sht20_temperature()))))
  print((str('HUM:') + str((pm25_sht20.get_sht20_humidity()))))
  wait_ms(2)
```

### PM2.5(SHT30 Version)

#> Obtain the values of pm2.5 particles and sht30 temperature and humidity values


<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_sht30_Demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

setScreenColor(0x222222)

pm25_sht30 = module.get(module.PM25_SHT30)

while True:
  print((str('SPM PM1.0:') + str((pm25_sht30.get_pm1_0_factory()))))
  print((str('SPM PM2.5:') + str((pm25_sht30.get_pm2_5_factory()))))
  print((str('SPM PM10:') + str((pm25_sht30.get_pm10_factory()))))
  print((str('ATE PM1.0:') + str((pm25_sht30.get_pm1_0_air()))))
  print((str('ATE PM2.5:') + str((pm25_sht30.get_pm2_5_air()))))
  print((str('ATE PM10:') + str((pm25_sht30.get_pm10_air()))))
  print((str('>3.0um Particles:') + str((pm25_sht30.get_num_above_0_3()))))
  print((str('TEM:') + str((pm25_sht30.get_sht30_temperature()))))
  print((str('HUM:') + str((pm25_sht30.get_sht30_humidity()))))
  wait_ms(2)
```

## API

### SHT20

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_get_num_above.svg">

```python
pm25_sht20.get_num_above_0_3()
```

- Retrieves the number of particles with a diameter greater than 0.3 (2.5/10) micrometers in the air, measured in particles per 0.1 liters of air. Returns an integer value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_get_pm_factory.svg">

```python
pm25_sht20.get_pm1_0_factory()
```

- Retrieves the PM1.0 (PM2.5, PM10) concentration value from the PM2.5 sensor (SHT20).
    - PM: Represents particulate matter concentration, usually measured in micrograms per cubic meter (µg/m³).
    - ATE: This option typically represents Air Quality Index (AQI) or another specific measurement standard, though the exact meaning may depend on the device or application definition.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht20_get_humidity.svg">

```python
pm25_sht20.get_sht20_humidity()
```

- Retrieves the relative humidity value, expressed as a percentage of relative humidity (%RH). Returns a floating-point number.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht20_get_temperature.svg">

```python
pm25_sht20.get_sht20_temperature()
```

- Retrieves the temperature value, measured in degrees Celsius (°C). Returns a floating-point number.

### SHT30

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht30_get_humidity.svg">

```python
pm25_sht30.get_sht30_humidity()
```

- Retrieves the relative humidity value, expressed as a percentage of relative humidity (%RH). Returns a floating-point number.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht30_get_num_above.svg">

```python
pm25_sht30.get_num_above_0_3()
```

- Retrieves the number of particles with a diameter greater than 0.3 (2.5/10) micrometers in the air, measured in particles per 0.1 liters of air. Returns an integer value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht30_get_pm_factory.svg">

```python
pm25_sht30.get_pm1_0_factory()
```

- Retrieves the PM1.0 (PM2.5, PM10) concentration value from the PM2.5 sensor (SHT30).
    - PM: Represents particulate matter concentration, usually measured in micrograms per cubic meter (µg/m³).
    - ATE: This option typically represents Air Quality Index (AQI) or another specific measurement standard, though the exact meaning may depend on the device or application definition.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/pm2.5/uiflow_block_pm25_sht30_get_temperature.svg">

```python
pm25_sht30.get_sht30_temperature()
```

- Retrieves the temperature value, measured in degrees Celsius (°C). Returns a floating-point number.