# MPU6050
Receive data from the MPU6050 over I2C. Some of the features of this chip is detailed below. As a reference: https://store.invensense.com/datasheets/invensense/MPU-6050_DataSheet_V3%204.pdf

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
  - The logic level for communications with the master is set by the voltage on VLOGIC.
  - VLOGIC may be 1.8V ± 5% or VDD.
  - The MPU6050 acts as a master to any external sensors connected to the auxilary I2C bus.

## Sensor data registers
  - Sensor data registers contain the latest gyro, accelerometer, auxilary sensor and temperature measurement data. They are read-nly registers and are accessed via the serial interface. Data from these registers may be read anytime. However, the interrupt function may be used to determine when new data is available (see section 8).

 ## Programmable interrupts
  - The MPU6050 has a programmable interrupt system which can generate an interrupt signal on the INT pin. Status flags indicate the source of an interrupt. Interrupt sources may be enable or disabled individually.
  ### Interrupt sources
  - FIFO Overflow (FIFO module)
  - Data Ready (Sensor registers)
  - I2C master errors 
  - I2C slave 4

