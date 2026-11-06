# Raspberry Pi Thermostat Prototype

A Python-based thermostat prototype developed using a Raspberry Pi, breadboard circuitry, temperature sensing, physical controls, LEDs, and an LCD display.

The project explores embedded systems by connecting software logic with physical hardware. It uses a state machine to manage thermostat modes, reads temperature and humidity from a sensor, and provides visual feedback through LEDs and an LCD.

## Features

- **Three thermostat modes:** Off, heat, and cool.
- **Temperature sensing:** Reads temperature and relative humidity from an AHTx0 sensor.
- **Adjustable setpoint:** Physical buttons increase or decrease the target temperature, starting at 72°F.
- **Visual status indicators:** Red and blue LEDs represent heating and cooling states.
- **PWM LED behavior:** LEDs pulse when the measured temperature indicates that heating or cooling is needed.
- **LCD interface:** A 16×2 display alternates between temperature information and thermostat status.
- **State-machine design:** Uses explicit states and transitions to manage thermostat behavior.
- **Serial communication:** Sends periodic thermostat status information over a serial connection.

## Hardware

The prototype uses the following components:

- Raspberry Pi
- Solderless breadboard
- AHTx0 temperature and humidity sensor
- 16×2 character LCD
- Red and blue LEDs
- Three physical push buttons
- Connecting wires and supporting circuit components

Refer to the included circuit and state diagrams for additional project documentation.

## Software and Technologies

- Python
- Raspberry Pi GPIO
- I²C communication
- Serial communication
- PWM LED control
- State-machine programming
- Multithreading
- Adafruit sensor and LCD libraries

## How It Works

### Thermostat States

The thermostat cycles through three operating modes:

| Mode | Behavior |
|---|---|
| Off | Both indicator LEDs are off. |
| Heat | The red LED indicates heating status. |
| Cool | The blue LED indicates cooling status. |

When heating is selected, the red LED pulses if the measured temperature is below the setpoint and remains on when the target is reached.

When cooling is selected, the blue LED pulses if the measured temperature is above the setpoint and remains on when the target is reached.

### Physical Controls

Three buttons provide direct interaction:

- Green button: Cycle between off, heat, and cool.
- Red button: Increase the temperature setpoint.
- Blue button: Decrease the temperature setpoint.

### Display

The LCD displays the current date and time on its first line. The second line alternates between the measured temperature and the selected thermostat mode with its setpoint.

### Serial Communication

The thermostat periodically sends a comma-separated status message containing:
- Current thermostat mode
- Current temperature in Fahrenheit
- Temperature setpoint in Fahrenheit

## Repository Contents

| File | Description |
|---|---|
| `Thermostat.py` | Main thermostat implementation |
| `TemperatureSensorIntegration.py` | Temperature sensor and LCD integration |
| `SerialLightControl-Server.py` | Serial-command-based LED control exercise |
| `Milestone1.py` | PWM LED fading exercise |
| `Milestone3.py` | Earlier project milestone implementation |
| `statediagram.drawio` | Editable state diagram |
| `milestone3.drawio.pdf` | Project milestone diagram |
| `module7statediagram.drawio.pdf` | Thermostat state diagram |
| `module7report.docx` | Project documentation and report |

Additional milestone documentation is included in the repository.

## What I Learned

This project gave me experience combining Python programming with physical hardware and embedded-system concepts.

I developed a better understanding of:
- Building and troubleshooting breadboard circuits.
- Interfacing with Raspberry Pi GPIO pins.
- Reading data from a temperature sensor.
- Using I²C and serial communication.
- Managing program behavior with a state machine.
- Using threads to handle ongoing display updates.
- Connecting software decisions to physical outputs.

It also reinforced the importance of careful wiring, code structure, and attention to detail when software interacts with hardware.

## Project Scope

This is an educational thermostat prototype developed as part of coursework in embedded systems. It demonstrates hardware/software integration and thermostat control logic; it is not a certified or production-ready heating and cooling controller.
