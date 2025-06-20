🔧 Throttle-by-Wire (TBW) System — Manual & Autonomous Modes
This project implements a Throttle-by-Wire control system capable of operating in both Manual and Autonomous modes using an Arduino-based setup. It simulates throttle input, processes analog and digital control signals, and drives a stepper motor via an L297 driver.

📦 Features
Dual Mode Operation:

Manual Mode: Throttle signal from a potentiometer is read via Arduino and converted into a 0–5V analog signal using an MCP4725 DAC.

Autonomous Mode: Throttle value is digitally commanded via I²C, then converted to analog voltage for the motor.

Signal Conditioning:

MCP4725 DAC output is buffered using an LM358 op-amp.

Analog signal is used to drive the CONTROL input of the L297 motor driver.

Motor Control:

L297 stepper motor driver used to drive a bipolar stepper motor.

Clock and direction signals managed via Arduino.

VREF and OSC pins configured for current control and timing.

System Power:

48V input stepped down using a buck converter (not shown in simulation).

Separate 12V rail used for motor and op-amp; 5V rail used for logic and DAC.

Safety and Status:

LED indicator turns ON when motor is actively driven.

Diodes and resistors protect the circuit from back EMF and simulate practical loading.

📐 Circuit Overview
MCP4725 → DAC for analog voltage generation.

LM358N → Buffer amplifier for throttle signal.

L297 → Stepper motor driver receiving analog throttle and digital control.

Stepper Motor → Actuated as simulated throttle response.

Arduino UNO → Central controller handling both manual and autonomous signal processing.

🔗 Technologies Used
Proteus 8.13 for simulation

Arduino Uno (ATmega328P)

I²C (for DAC communication)

Analog signal processing with op-amps

Stepper motor driver (L297)

🚦 Modes Summary
Mode	Throttle Source	Output Type	Path Used
Manual	Potentiometer	Analog	A2 reads → DAC → Op-amp → L297
Autonomous	Digital Command	Analog	I²C to DAC → Op-amp → L297

📸 Screenshots
✅ Complete Proteus simulation

✅ Working DAC to motor control

✅ Logic switching & mode handling

🚀 Future Improvements
Integrate encoder feedback for closed-loop speed control

Add CAN/UART-based throttle data reception

Real-world PCB implementation and field testing

