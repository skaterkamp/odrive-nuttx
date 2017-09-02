README
======

The NuttX configuration for the ODriveRobotics ODrive v3.3 is based on the configuration
Olimex STM32-H405.

It was tested with the Debian ARM NONE EABI toolchain (binutils-arm-none-eabi
gcc-arm-none-eabi gdb-arm-none-eabi).

For flashing Debian openocd package and a ST-LINK/V2 debug tool is needed.

Make sure that '# CONFIG_NSH_CONDEV is not set' is in the .config file - it defaults
to '/dev/console' which makes problems with the shell over USB.

The following peripherals are enabled in this configuration.
 - LED:        Shows the sytem status

 - Button:     Built in app 'buttons' works.

 - ADC:        ADC1 samples ADC_IN1. Built in app 'adc' works.

 - USB-FS-OTG: The console is running on the virtual serial port. Note that you
               have to press enter three times until NSH appears.

 - CAN:        Built in app 'can' is enabled but not tested, since no CAN transceiver
               is on board.


Taken from the discovery board README, checkme:
Debugging
---------
If you are going to use a debugger, you should make sure that the following
settings are selection in your configuration file:

 CONFIG_DEBUG_SYMBOLS=y     : Enable debug symbols in the build
 CONFIG_ARMV7M_USEBASEPRI=y : Use the BASEPRI register to disable interrupts
