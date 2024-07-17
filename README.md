# 8051 Microcontroller-based Alcohol Detector with Buzzer #

This project implements an alcohol detector using the 8051 microcontroller. The system detects the presence of alcohol and activates a buzzer to alert.

## Table of Contents

- [Introduction]
- [Components]
- [Circuit Diagram]
- [Code]
- [How it Works]
- [Installation]
- [Usage]
- [Contributing]

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

## Code

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

Once the setup is complete, power on the system. 
The alcohol detector will start monitoring the air for alcohol concentration. 
If alcohol is detected above the threshold, the buzzer will sound an alert.

## Contributions

Contributions are welcome! Please fork this repository and submit pull requests with improvements and bug fixes.


## Thank You! ##
