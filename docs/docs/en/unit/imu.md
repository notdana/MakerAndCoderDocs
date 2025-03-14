# Mini Unit IMU

## Example

Gets the current gyroscope status

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

setScreenColor(0x222222)
unit_imu_0 = unit.get(unit.IMU6886, unit.PORTA)

unit_imu_0.setAccUnit(0)
unit_imu_0.gyroFullScaleRange(0x00)
while True:
  print((str('ACC Z:') + str((unit_imu_0.acceleration[0]))))
  print((str('ACC Y:') + str((unit_imu_0.acceleration[1]))))
  print((str('ACC Y:') + str((unit_imu_0.acceleration[2]))))
  print((str('Gyro X:') + str((unit_imu_0.gyro[0]))))
  print((str('Gyro Y:') + str((unit_imu_0.gyro[1]))))
  print((str('Gyro Z:') + str((unit_imu_0.gyro[2]))))
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_acc_fullscale_range.svg">

```python
unit_imu_0.accFullScaleRange(0x00)
```

- Set the full range of acceleration scales

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_acc_x.svg">

```python
print(unit_imu_0.acceleration[0])
```

- Get the value of the accelerometer on the X-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_acc_y.svg">

```python
print(unit_imu_0.acceleration[1])
```

- Get the value of the accelerometer on the Y-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_acc_z.svg">

```python
print(unit_imu_0.acceleration[2])
```

- Get the value of the accelerometer on the Z-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_gyr_x.svg">

```python
print(unit_imu_0.gyro[0])
```

- Get the value of the gyroscope on the X-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_gyr_y.svg">

```python
print(unit_imu_0.gyro[1])
```

- Get the value of the gyroscope on the Y-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_gyr_z.svg">

```python
print(unit_imu_0.gyro[2])
```

- Get the value of the gyroscope on the Z-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_x.svg">

```python
print(unit_imu_0.ypr[1])
```

- Get the attitude angle on the X-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_get_y.svg">

```python
print(unit_imu_0.ypr[2])
```

- Get the attitude angle on the Y-axis

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_gyro_calibrate.svg">

```python
unit_imu_0.gyroCalibrate(250, 5)
```

- Set gyroscope calibration using the number of samples and delay per sample

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_gyro_fullscale_range.svg">

```python
unit_imu_0.gyroFullScaleRange(0x00)
```

- Set the gyroscope scale range

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_set_acc_unit.svg">

```python
unit_imu_0.setAccUnit(0)
```

- Set the accelerometer unit to g or m/s^2

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/imu/uiflow_block_unit_imu_set_gyro_offset.svg">

```python
unit_imu_0.setGyroOffsets(0, 0, 0)
```

- Set manual gyroscope calibration offset values

