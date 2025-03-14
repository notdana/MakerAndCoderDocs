# Module13.2 Stepmotor Driver

## Example

> Initialize the I2C address and frequency settings for the stepper motor, set the direction for motors X and Y, read the device's firmware version and I2C address, and then in the loop, execute the reset for motors X and Y, enable/disable the motors, and switch the status at certain time intervals.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_demo.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time

setScreenColor(0x000000)

stepmotor = module.get(module.STEPMOTORDRIVER)

stepmotor.initDevice(0x27)
stepmotor.setStepPulse(500, 0)
stepmotor.setStepPulse(500, 1)
stepmotor.setStepPulse(500, 2)
stepmotor.setStepDir(0, 1)
stepmotor.setStepDir(1, 1)
stepmotor.enableMotor(1)
print(stepmotor.readStatus(0XFE))
print(stepmotor.readStatus(0XFF))
while True:
  stepmotor.resetMotor(0, 1)
  wait(2)
  stepmotor.resetMotor(1, 1)
  wait(2)
  stepmotor.enableMotor(0)
  wait(2)
  stepmotor.enableMotor(1)
  wait(2)
  stepmotor.resetMotor(0, 0)
  wait(2)
  stepmotor.resetMotor(1, 0)
  wait(2)
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_enable_motor.svg">

```python
stepmotor.enableMotor(0)
```

- This command is used to disable the running state of all stepper motors. With this block, the user can enable or disable all motors connected to the driver.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_init.svg">

```python
stepmotor.initDevice(0x27)
```

- This command initializes the I2C address of the stepper motor driver to 0x27, which is used to set the I2C communication address for the motor driver. The I2C address is used to uniquely identify the device in the system, ensuring that the host can communicate correctly.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_modbus_init.svg">

```python
stepmotor.modbus_init(26, 34, 115200, 1, 1)
```

- This command initializes the stepper motor driver communication via the Modbus protocol. The parameters are as follows:
    - Tx 26: Specifies the pin number for sending data.
    - Rx 34: Specifies the pin number for receiving data.
    - baudrate 115200: Sets the Modbus communication baud rate to 115200bps.
    - mode Master: Sets the communication mode as Master, meaning the current device controls the slave device.
    - slave addr 1: Specifies the slave device address as 1.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_read_device_status.svg">

```python
stepmotor.readStatus(0XFE)
```

- This command reads the firmware version of the stepper motor driver. By obtaining the firmware version, users can verify if the driver firmware matches expectations, facilitating version management and updates.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_read_fault_status.svg">

```python
stepmotor.readFaultPinStatus(0)
```

- This command reads the fault status of a specific motor (such as motor X). By using this command, users can check if the motor has any abnormal conditions, such as overcurrent, overheating, or communication failure.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_read_io_status.svg">

```python
stepmotor.readIOstatus()
```

- This command reads the input/output (IO) status of all limit switches. Limit switches are typically used to ensure that the motor stops when reaching the extreme position. This command allows users to monitor the status of multiple limit switches.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_read_pin_status.svg">

```python
stepmotor.readPinStatus(0)
```

- This command reads the status of a specific limit switch (such as IO 0) to determine if the limit switch has been triggered. When a limit switch is triggered, it usually indicates that the motor has reached a physical limit, and the system can take protective measures based on this information.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_reset.svg">

```python
stepmotor.resetMotor(0, 1)
```

- This command resets motor X and sets its state to TRUE. The reset operation will restore the motor to its initial state, clearing any errors or warning states, allowing it to operate normally.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_set_i2c.svg">

```python
stepmotor.setI2cAddress(0x27)
```

- This command sets the I2C communication address of the stepper motor driver to 0x27. By setting the I2C address, the host can communicate with the driver and ensure both sides correctly recognize each other.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_set_micro_stepselect.svg">

```python
stepmotor.setMicroStepSelect(0)
```

- This command sets the stepper motor to "full step" mode. In full step mode, each motor step is a complete step. This setting affects the motor's precision and speed.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_set_single_motor.svg">

```python
stepmotor.singleMotorCtrl(0, 0)
```

- This command sets the status of a single motor X to "pause." The pause operation temporarily stops the motor's movement without affecting its current position. The motor can resume operation later.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_set_step_dir.svg">

```python
stepmotor.setStepDir(0, 0)
```

- This command sets the running direction of motor X to "reverse." The motor's direction determines its rotation direction, and changing this setting controls the motor's rotation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_driver_set_step_pulse2.svg">

```python
stepmotor.setStepPulse(500, 0)
```

- This command sets the pulse frequency of motor X to 500Hz. The pulse frequency affects the running speed of the stepper motor. The higher the frequency, the faster the motor rotates.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

- This command reads the coil status of slave device address 1, starting at address 1, with a coil count of 0. This operation can monitor the status of the motor driver and ensure the motor's safe operation.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

- This command reads discrete inputs from Modbus slave device address 1, starting at address 1

, reading 0 inputs. This is a commonly used operation in the Modbus protocol, typically for reading the status of switches, buttons, and other digital inputs.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

- This command reads the holding registers from slave device address 1, starting at address 1, with 0 registers to read. Signed True means the read value is signed. These registers are typically used for storing device parameters or status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

- This command reads the input registers from Modbus slave device address 1, starting at address 1, reading 0 registers, and the read value is signed. Input registers are usually used to store data from sensors.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

- This command writes output values to multiple coils at slave device address 1. Starting address is 1, output value is 0. Coils are typically used to control the on/off state of devices or switches.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

- This command writes values to multiple registers at slave device address 1. Starting address is 1, register value is 0, and the value is signed. This is used to update configuration or status in the device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

- This command writes a value to a single coil at slave device address 1. Output address is 1, output value is 0. This operation is typically used to control a single device or function.
  

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_master_u_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

- This command writes a value to a single register at slave device address 1, with register address 1, register value 0, and the value is signed. This operation is commonly used for writing configuration parameters or controlling devices.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_fun_status.svg">

```python
1~6,15,16
```

- This command is used to define the function code used in Modbus communication. Here it is set to `READ_COILS_STATUS`, which means reading coil status. The function codes commonly used are:
    - READ_COILS_STATUS: Reads the status of coils, typically used to read the status of digital outputs.
    - READ_INPUT_STATUS: Reads the status of inputs, typically used to read the status of digital inputs.
    - READ_HOLDING_REGISTERS: Reads holding registers, usually used to read writable data registers.
    - READ_INPUT_REGISTERS: Reads input registers, typically used to read read-only analog input data.
    - WRITE_SINGLE_COIL: Writes a value to a single coil, typically used to set the status of digital outputs.
    - WRITE_SINGLE_REGISTER: Writes a value to a single holding register, typically used to write data to a register.
    - WRITE_MULTIPLE_COILS: Writes values to multiple coils, typically used to set the status of multiple digital outputs.
    - WRITE_MULTIPLE_REGISTERS: Writes values to multiple holding registers, typically used to write a series of registers.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

- This command is used to retrieve the address of the Modbus slave device. This operation is crucial for retrieving data from multiple devices and ensures that commands are sent to the correct device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

- This command is used to retrieve the function code used in the current Modbus request. It is important for debugging and verifying whether the device operation is correct.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

- This command retrieves the number of registers or coils to be read or written. This parameter determines how much data is involved in the current Modbus command.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

- This command initializes the Modbus slave device's function code operation, setting the starting address to 0 and reading 0 coils. This command is used to begin the operation of reading coil status.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

- This command receives the Application Data Unit (ADU) request, which is the data frame transmitted in the Modbus protocol. The device understands the received data through this request.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(0)
```

- This command sends an ADU response containing the response data of the Modbus slave device. This operation is usually performed after the device finishes processing the request and returns the result to the master device.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

- This command updates the `READ_COILS_STATUS` function code of the Modbus slave device. It sets the starting address to 0, reads 0 coils, and uses a list to store the data returned by the slave device. This command is usually used to update the coil status after the device receives a data request.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_any.svg">

```python
modbus._mdbus_uart.any()
```

- This command checks whether there is data in the UART buffer. This is very important in serial communication, ensuring that the device can handle and read any unprocessed data.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_read.svg">

```python
modbus._mdbus_uart.read()
```

- This command reads all available data in the UART buffer. It is typically used to empty the buffer and process all received data in serial communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_readline.svg">

```python
modbus._mdbus_uart

.readline()
```

- This command reads a line of data from the UART until it encounters a newline character. It is commonly used for data that is transmitted in line format, such as sensor readings or logging.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

- This command reads a specified number of characters (here 10) from the UART. It is useful for fixed-length data transmissions, such as reading data in a specific format from sensors.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_write.svg">

```python
modbus._mdbus_uart.write('')
```

- This command writes data through UART, with the content inside the quotation marks being written. It is used for data transmission in serial communication.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

- This command writes a line of data through UART and automatically appends a newline character. It is typically used for sending data in line format, making it easier for the receiver to process line-by-line.

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/stepmotor_driver/uiflow_block_stepmotor_uart_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```

- This command sends raw data via UART. In this example, the raw data is constructed as a list with three elements [0, 0, 0], representing the transmission of three bytes of raw data. This command is commonly used in serial communication when precise control over the transmitted byte data is needed, such as controlling external devices or transmitting low-level protocol data.
