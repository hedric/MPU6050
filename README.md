# MPU6050
Basic project to receive data from the MPU-6050 over I2C. . This will be implemented on two different development boards.

- Tiva C Launchpad with a TM4C123G microcontroller, 32-bit ARM Cortex M4 CPU.
- Nucleo 144 F767ZI with a STM32F7 microcontroller, 32-bit ARM Cortex M7 CPU.

Some of the features of the MPU-6050 is detailed below.

## Data sheet
https://store.invensense.com/datasheets/invensense/MPU-6050_DataSheet_V3%204.pdf

## Regiser map
https://www.invensense.com/wp-content/uploads/2015/02/MPU-6000-Register-Map1.pdf

## Resources
 - https://electronics.stackexchange.com/questions/172266/getting-gyro-values-from-mpu-6050
 - https://playground.arduino.cc/Main/MPU-6050#sketch

## Gyroscope
 * Digital-output X-, Y-, and Z-Axis angular rate sensors (gyroscopes) with a user-programmable full-scale range of ±250, ±500, ±1000 and ±2000 degrees/sec.

## Accelerometer
  * Digital-output triple-axis accelerometer with a programmable full scale range of ±2g, ±4g, ±8g, and ±16g.
  * User-programmable interrupts
  * High-G interrupt.

## Additional
  * 9-Axis MotionFUsion by the on-chip Digital Motion Processor (DMP).
  * Auxilary master I2C bus for reading data from external sensors (e.g., magnetometer).
  * Digital-ouput temperature sensor.
  * 400 kHz fast mode I2c for communicating with all registers.

## Important information
  - VDD = 3.3V
  - Slave adress of MPU6050 is b110100X which is 7 bits. The X bit can be either 1 or 0 depending on if there are two MPU6050 on the I2C bus.
  - b1101001 = 0x69 -> AD0 pin to VLOGIC (+3.3V)
  - b1101000 = 0x68 -> AD0 pin to GND
  - The logic level for communications with the master is set by the voltage on VLOGIC.
  - VLOGIC may be 1.8V ± 5% or VDD.
  - The MPU6050 acts as a master to any external sensors connected to the auxilary I2C bus.

## Sensor data registers
  - Sensor data registers contain the latest gyro, accelerometer, auxilary sensor and temperature measurement data. They are read-nly registers and are accessed via the serial interface. Data from these registers may be read anytime. However, the interrupt function may be used to determine when new data is available (see section 8).

 ## Programmable interrupts
  - The MPU6050 has a programmable interrupt system which can generate an interrupt signal on the INT pin. Status flags indicate the source of an interrupt. Interrupt sources may be enable or disabled individually.
  ### Interrupt sources
  - FIFO Overflow (FIFO module).
  - Data Ready (Sensor registers).
  - I2C master errors.
  - I2C slave 4.
 
 ## I2C communications protocol
  - Start condition: While SCL high, SDA high -> low.
  - Stop condition: While SCL high, SDA low -> high.
  - I2C data bytes are 8-bits long.
  - Acknowledge: SDA low while SCL high at 9th clock cycle.
  - Not Acknowledge: SDA high while SCL high at 9th clock cycle.
  
  ### Reading the internal MPU6050 registers
   - S = Start condition
   - AD = Slave I2C adress
   - W = Write bit (0)
   - R = Read bit (1)
   - ACK = Acknowledge
   - NACK = Not-Acknowledge

