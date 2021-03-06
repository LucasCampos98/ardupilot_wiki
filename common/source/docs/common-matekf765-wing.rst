.. _common-matekf765-wing:

==================
Mateksys F765-Wing
==================

.. image:: ../../../images/matekf765-wing.jpg
    

the above image and some content courtesy of `mateksys.com <http://www.mateksys.com/?portfolio=f765-wing>`__

.. note::

   Support for this board is available with ArduPilot 4.0 and higher

Specifications
==============

-  **Processor**

   -  STM32F765VIT6  ARM (216MHz)


-  **Sensors**

   -  InvenSense MPU6000 IMU (accel, gyro) & ICM20602
   -  BMP280 barometer
   -  Voltage & 132A current sensor


-  **Power**

   -  9V ~ 36V DC input power
   -  5V 2A BEC for peripherals
   -  9/12V 2A BEC for video
   -  5/6/7.2V 8A BEC for servos


-  **Interfaces**

   -  7x UARTS
   -  12x PWM outputs
   -  1x RC input PWM/PPM, SBUS
   -  2x I2C ports for external compass, airspeed sensor, etc.
   -  SPI4 port
   -  USB port
   -  6 ADC
   -  Dual Switchable Camera inputs
   -  Built-in OSD


-  **Size and Dimensions**

   - 54mm x 36mm x 13mm
   - 26g

See mateksys.com for more `detailed specifications <http://www.mateksys.com/?portfolio=f765-wing#tab-id-2>`__ and `wiring diagrams <http://www.mateksys.com/?portfolio=f765-wing#tab-id-4>`__ (ArduPilot connections may vary slightly due to different UART useage).
   
Default UART order
==================

- SERIAL0 = console = USB
- SERIAL1 = Telemetry1 = UART7 (support CTS and RTS signaling)
- SERIAL2 = Telemetry2 = USART1
- SERIAL3 = GPS1 = USART2
- SERIAL4 = GPS2 = USART3
- SERIAL5 = USER = UART8
- SERIAL6 = USER = UART4

UART6 RX is used for RC input and supports all ArduPilot serial protocols

Serial port protocols (Telem, GPS, etc.) can be adjusted to personal preferences.

Dshot capability
================

All motor/servo outputs are Dshot and PWM capable. However, mixing Dshot and normal PWM operation for outputs is restricted into groups, ie. enabling Dshot for an output in a group requires that ALL outputs in that group be configured and used as Dshot, rather than PWM outputs. The output groups that must be the same (PWM rate or Dshot, when configured as a normal servo/motor output) are: 1/2, 3/4, 5/6,  or 7/8/9/10. Outputs 11 and 12 are not Dshot capable.

Where to Buy
============

- see this list of `Mateksys Distributors <http://www.mateksys.com/?page_id=1212>`__

Connecting a GPS/Compass module
===============================

This board does not include a GPS or compass so an :ref:`external GPS/compass <common-positioning-landing-page>` should be connected in order for autonomous modes to function.

If the GPS is attached to UART2 TX/RX and powered from the adjacent 4.5V pins, it will be powered when connected via USB, as would the RX if powered from the adjacent 4.5V pins to UART6.

A battery must be plugged in for power to be provided to the pins marked 5V on the board.