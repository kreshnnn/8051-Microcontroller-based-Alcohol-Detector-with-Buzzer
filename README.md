# 8051 Microcontroller-based Alcohol Detector with Buzzer #

This project implements an alcohol detector using the 8051 microcontroller. The system detects the presence of alcohol and activates a buzzer to alert.

## Table of Contents

1. [Aim](#aim)
2. [Introduction](#introduction)
3. [Components](#components)
4. [Circuit Diagram](#circuit-diagram)
5. [Code](#code)
6. [How it Works](#how-it-works)
7. [Installation](#installations)
8. [Usage](#usage)
9. [Applications](#applications)
10. [Advantages](#advantages)
11. [Limitations](#limitations)
12. [Future Scope](#future-scope)
13. [Bill of Materials](#bill-of-materials)
14. [Contributions](#contributions)
15. [Project Status](#project-status)
16. [License](#license)

## Aim

To monitor alcohol levels and provide an indication using a buzzer and an LCD interface.

## Introduction

The 8051 Microcontroller-based Alcohol Detector with Buzzer is designed to detect alcohol concentration in the air. When alcohol is detected above a certain threshold, the system triggers a buzzer to alert. This project is useful for applications such as vehicle driver alcohol detection and workplace safety monitoring.

## Components

- 8051 Microcontroller
- MQ-3 Alcohol Sensor
- Buzzer
- Resistors
- Capacitors
- Connecting wires
- Power supply

## Code for Interfacing

```
// The code for the 8051 microcontroller is written in C.
// The following components are connected to the microcontroller:
// - Buzzer: Connected to Port 1 Pin 0
// - MQ-3 Alcohol Sensor: Connected to Port 1 Pin 1

#include <reg51.h>

sbit buzzer = P1^0; // Buzzer connected to Port 1 Pin 0
sbit sensor = P1^1; // MQ-3 sensor output connected to Port 1 Pin 1

void delay(unsigned int time) {
    unsigned int i, j;
    for (i = 0; i < time; i++)
        for (j = 0; j < 1275; j++);
}

void main(void) {
    while(1) {
        if (sensor == 1) {
            buzzer = 1; // Turn on buzzer
            delay(1000); // Delay for a second
        } else {
            buzzer = 0; // Turn off buzzer
        }
    }
}
```

## How it Works

1. Alcohol Detection: The MQ-3 alcohol sensor detects the presence of alcohol in the air.
2. Signal Processing: The sensor output is connected to the 8051 microcontroller.
3. Alert Mechanism: When the alcohol concentration exceeds a certain threshold, the microcontroller activates the buzzer.

## Installation

1. Hardware Setup: Connect the components as per the circuit diagram.
2. Software Setup: Load the provided code into the 8051 microcontroller using an appropriate programmer.

## Usage

- Once the setup is complete, power on the system. 
- The alcohol detector will start monitoring the air for alcohol concentration. 
- If alcohol is detected above the threshold, the buzzer will sound an alert.

## Applications

- Used for detecting alcohol levels in a person's breath for safety purposes.
- Can be integrated into vehicles or workplaces to monitor alcohol consumption.
- Useful in law enforcement for checking DUI (Driving Under the Influence) levels.

## Advantages

- Provides a quick and easy method to detect alcohol levels.
- Compact design and easy to integrate with other systems like car ignition or workplace safety protocols.
- Uses a simple microcontroller (8051), making it cost-effective and energy-efficient.

## Limitations

- Limited detection range and may not be as accurate as professional alcohol testing devices.
- Requires regular calibration to ensure accuracy.
- Dependent on environmental factors, such as temperature and humidity, which could affect sensor performance.

## Future Scope
Integration with smartphones or mobile apps for real-time monitoring and notifications.
Enhancing accuracy by using more advanced sensors or adding multi-sensor capabilities.
Expansion of the system to include additional safety features like automatic vehicle shutdown when alcohol is detected.

## Bill of Materials

The bill of materials for this project includes all the components listed above, with an estimated cost of ₹2500-₹3000.

## Contributions

Contributions are welcome! Please fork this repository and submit pull requests with improvements and bug fixes.

## Project Status

Finished — The primary Alcohol Detection system has been developed. Future improvements, such as new features and more advanced forecasting methods, are welcome.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

## Thank You! ##
