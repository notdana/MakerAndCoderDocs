# [Unit TimerPWR](/en/unit/Unit-TimerPWR)

## Example

> Get battery, USB, and Grove port status information from the TimerPWR module, configure various functions of the module (such as button, Grove output, OLED backlight, etc.), and handle events related to device sleep and wake-up.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/uiflow_block_unit_timerpwr_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import unit

timerpwr_1 = unit.get(unit.TIMERPWR, unit.PORTA)

timerpwr_1.init_i2c_address(0x56)

timerpwr_1.set_oled_backlight_status(True)
timerpwr_1.set_wakeup_trigger(timerpwr_1.TRIG_ALL)
while True:
  timerpwr_1.sleep_cycle(0, 0, 5, 0, 0, 5)
  print(timerpwr_1.get_battery_voltage())
  print(timerpwr_1.get_battery_current())
  print(timerpwr_1.get_usb_voltage())
  print(timerpwr_1.get_usb_current())
  print(timerpwr_1.get_grove_voltage())
  print(timerpwr_1.get_grove_current())
  print(timerpwr_1.get_firmware_version())
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/1_uiflow_block_unit_timerpwr_init.svg">

```python
timerpwr_1.init_i2c_address(0x56)
```

- Initializes the TimerPWR module’s I2C address to 0x56. This address is used to communicate with the module over the I2C bus.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/2_uiflow_block_unit_timerpwr_get_battery_voltage.svg">

```python
timerpwr_1.get_battery_voltage()
```

- Gets the current battery voltage value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/3_uiflow_block_unit_timerpwr_get_battery_current.svg">

```python
timerpwr_1.get_battery_current()
```

- Gets the current battery current value.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/4_uiflow_block_unit_timerpwr_get_usb_voltage.svg">

```python
timerpwr_1.get_usb_voltage()
```

- Gets the current USB port voltage.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/5_uiflow_block_unit_timerpwr_get_usb_current.svg">

```python
timerpwr_1.get_usb_current()
```

- Gets the current USB port current.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/6_uiflow_block_unit_timerpwr_get_grove_voltage.svg">

```python
timerpwr_1.get_grove_voltage()
```

- Gets the voltage of the external device connected to the Grove port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/7_uiflow_block_unit_timerpwr_get_grove_current.svg">

```python
timerpwr_1.get_grove_current()
```

- Gets the current information of the Grove port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/8_uiflow_block_unit_timerpwr_get_button_status.svg">

```python
timerpwr_1.get_button_status(0)
```

- 0 is the button number, and this returns whether the button is pressed or not.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/9_uiflow_block_unit_timerpwr_get_grove_output_status.svg">

```python
timerpwr_1.get_grove_output_status()
```

- Returns the current enable/disable status of the Grove output port.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/10_uiflow_block_unit_timerpwr_get_oled_backlight_status.svg">

```python
timerpwr_1.get_oled_backlight_status()
```

- Returns whether the OLED backlight is currently turned on.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/11_uiflow_block_unit_timerpwr_get_firmware_version.svg">

```python
timerpwr_1.get_firmware_version()
```

- Gets the current firmware version of the TimerPWR module.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/12_uiflow_block_unit_timerpwr_save_data_to_flash.svg">

```python
timerpwr_1.save_data_to_flash()
```

- Saves data to flash memory. This block stores data (such as battery, current, etc.) in persistent storage for later use.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/13_uiflow_block_unit_timerpwr_set_grove_output_status.svg">

```python
timerpwr_1.set_grove_output_status(True)
```

- Enables the Grove output port by setting its status to True.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/14_uiflow_block_unit_timerpwr_set_oled_backlight_status.svg">

```python
timerpwr_1.set_oled_backlight_status(True)
```

- Enables the OLED backlight by setting its status to True.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/15_uiflow_block_unit_timerpwr_set_wakeup_trigger.svg">

```python
timerpwr_1.set_wakeup_trigger(timerpwr_1.TRIG_ALL)
```

- Sets the wake-up trigger condition to all events (TRIG_ALL). This block configures the module to wake up on any event (such as button press, USB insertion, etc.).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/16_uiflow_block_unit_timerpwr_set_sleep_trigger.svg">

```python
timerpwr_1.set_sleep_trigger(timerpwr_1.TRIG_ALL)
```

- Sets the sleep trigger condition to all events (TRIG_ALL). This block configures the module to enter sleep mode on any event to save power.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/17_uiflow_block_unit_timerpwr_sleep_once.svg">

```python
timerpwr_1.sleep_once(0, 0, 5, 0, 0, 5)
```

- Sets a one-time sleep mode with timed sleep configuration (e.g., entering sleep mode every 5 seconds). This makes the device enter sleep mode and wake up after the specified time.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/18_uiflow_block_unit_timerpwr_sleep_cycle.svg">

```python
timerpwr_1.sleep_cycle(0, 0, 5, 0, 0, 5)
```

- Sets a cyclic sleep mode. This block makes the device periodically enter sleep mode and wake up (e.g., entering sleep mode every 5 seconds).

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/19_uiflow_block_unit_timerpwr_usb_callback.svg">

```python
def timerpwr_1_btna_released_event(args):
  # global params
  pass
timerpwr_1.set_callback(timer

pwr_1.EVENT_BUTTONA_RELEASED, timerpwr_1_btna_released_event)
```

- Sets a callback function for the EVENT_BUTTONA_RELEASED event. This event triggers the `timerpwr_1_btna_released_event` function when button A is released. The `args` parameter contains relevant data when the event is triggered.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/20_uiflow_block_unit_timerpwr_charging_callback.svg">

```python
def timerpwr_1_charging_event(args):
  # global params
  pass
timerpwr_1.set_callback(timerpwr_1.EVENT_CHARGING, timerpwr_1_charging_event)
```

- Sets a callback function for the EVENT_CHARGING event. This event triggers the `timerpwr_1_charging_event` function when the charging status changes.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/21_uiflow_block_unit_timerpwr_button_callback.svg">

```python
def timerpwr_1_usb_inserted_event(args):
  # global params
  pass
timerpwr_1.set_callback(timerpwr_1.EVENT_USB_INSERTED, timerpwr_1_usb_inserted_event)
```

- Sets a callback function for the EVENT_USB_INSERTED event. This event triggers the `timerpwr_1_usb_inserted_event` function when USB is inserted.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/unit/timerpwr/22_uiflow_block_unit_timerpwr_tick.svg">

```python
timerpwr_1.tick()
```

- Updates and processes the internal state of the TimerPWR module. It is typically called within a loop to ensure the module’s operational status and event handling.