# ATmega32 Smart Room Project

This is an Atmel Studio project that implements a smart room control system using the ATmega32 microcontroller, written in C. The project features a real-time clock display, lighting control, automatic curtain operation, and a secure password access system. Additionally, a Proteus project file is provided for simulation and testing purposes.

## Features

- Time Display: Real-time clock shown on the LCD, updated every second. Time setting via serial command.
- Lighting Control: Adjust room brightness (0-100%) via serial command, with current intensity shown on the LCD.
- Curtain Control: Open/close curtains via serial commands, with status displayed on the LCD.
- Secure Access: Password-protected (1234) serial control, auto-logout after 1 minute, requires re-entry to access.
- Help Command: Displays a list of supported commands for user reference.

## Hardware Components

- ATmega32 Microcontroller: The brain of the system, managing all inputs, outputs, and logic.
- LCD Display: Used to show the current time, date, curtain status, and light intensity.
- DS3232 RTC Module: Maintains accurate time and date.
- Stepper Motor: Controls the opening and closing of the curtains.
- Relay: Used to control the room lighting.
- Serial Port: Enables interaction with the system via UART for setting time, controlling the lamp, and operating the curtains.

## Libraries Used

- Liquid_crystal: Handles LCD communication.
- I2c_Lib: Low-level library for I2C communication.
- DS3232: Library for interfacing with the DS3232 RTC module.
- TWI: Another low-level I2C communication library.
- IO_Macros: Macros used by the TWI library.
- Serial: Manages serial communication with interrupt support.

## Proteus Schematic

![Datapath](https://i.imgur.com/aXFk1Vo.png)

## Simulating the Project

1. Open the provided Proteus project file `SmartRoom.pdsprj` in Proteus.
2. Click on the ATmega32 component to open its properties.
3. In the properties window, find the `Program File` section and click on the folder icon.
4. Navigate to the `Debug` folder within your Atmel Studio project directory.
5. Select the `SmartRoom.hex` file and click "Open."
6. Close the properties window.
7. Run the simulation by clicking the "Play" button in Proteus.

## Serial Commands

Set the time

```bash
set time HH:MM:SS M/D/Y
```

Adjust the lamp brightness

```bash
set lamp LEVEL
```

Control the curtains

```bash
open curtain
close curtain
```

List available commands

```bash
help
```

## Notes

- The curtain system assumes 190° motor rotation for full operation.
- The default password for accessing the system is 1234.
- Ensure that the correct time and date are set initially to maintain accurate RTC operation.
- The system auto-logs out after one minute of inactivity to secure the environment.

## License

This project is licensed under the MIT License.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
