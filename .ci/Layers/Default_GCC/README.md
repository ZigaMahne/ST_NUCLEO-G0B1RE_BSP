# Board: STMicroelectronics [NUCLEO-G0B1RE](https://www.st.com/en/evaluation-tools/nucleo-g0b1re.html)

## Default GCC Board Layer

Device: **STM32G0B1RETx**

System Core Clock: **64 MHz**

This setup is configured using **STM32CubeMX**, an interactive tool provided by STMicroelectronics for device configuration.
Refer to ["Configure STM32 Devices with CubeMX"](https://open-cmsis-pack.github.io/cmsis-toolbox/CubeMX/) for additional information.

### System Configuration

| System resource       | Setting
|:----------------------|:--------------------------------------
| Heap                  | 64 kB (configured in the STM32CubeMX)
| Stack (MSP)           |  1 kB (configured in the STM32CubeMX)

### STDIO mapping

**STDIO** is routed to Virtual COM port on the ST-LINK (using **USART2** peripheral)

### CMSIS-Driver mapping

| CMSIS-Driver          | Peripheral            | Board connector/component                             | Connection
|:----------------------|:----------------------|:------------------------------------------------------|:------------------------------
| Driver_GPIO0          | GPIO                  | Arduino digital I/O pins D2..D12, D14..D19            | ARDUINO_UNO_D2..D12, D14..D19
| Driver_I2C1           | I2C1                  | Arduino I2C pins D20..D21                             | ARDUINO_UNO_I2C
| Driver_USART1         | USART1                | Arduino UART pins D0..D1                              | ARDUINO_UNO_UART
| Driver_USART2         | USART2                | ST-LINK connector (CN2)                               | STDIN, STDOUT, STDERR
| CMSIS-Driver VIO      | GPIO                  | LED (LD4) and USER button (B1)                        | CMSIS_VIO

Reference to [Arduino UNO connector description](https://open-cmsis-pack.github.io/cmsis-toolbox/ReferenceApplications/#arduino-shield).

### CMSIS-Driver Virtual I/O mapping

| CMSIS-Driver VIO      | Board component
|:----------------------|:--------------------------------------
| vioBUTTON0            | USER button (B1)
| vioLED0               | LED Green   (LD4)

> **Note:**  Layer has been created with Firmware Package STM32Cube_FW_G0_V1.6.2.
