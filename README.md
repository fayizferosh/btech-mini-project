# Electronic Lock based on DTMF along with LCD Display

> An [electronic lock](https://en.wikipedia.org/wiki/Electronic_lock) which can be unlocked when the correct passcode is entered though a [DTMF](https://en.wikipedia.org/wiki/Dual-tone_multi-frequency_signaling) Keypad accompanied by a 16x2 [LCD](https://en.wikipedia.org/wiki/Liquid-crystal_display) Display which displays the same. When the passcode is entered in the [DTMF](https://en.wikipedia.org/wiki/Dual-tone_multi-frequency_signaling) Keypad, that data is decoded and the necessary details are sent to a 16x2 [LCD](https://en.wikipedia.org/wiki/Liquid-crystal_display) Display to display the same and is also compared with the already set passcode \[which can be altered if necessary, only by entering the current passcode (as a security measure)\] and if they are same sends the necessary signals to unlock the [electronic fail-secure lock](https://en.wikipedia.org/wiki/Electronic_lock).

| <img src="https://github.com/fayizferosh/btech-mini-project/assets/63997454/9e2776d3-289e-4bb1-a58c-d7cf3cc67d96"  width="35%" height="35%"> |
|:--:|
| *16x2 LCD Display with a DTMF Keypad* |

## Introduction

The main objective of our design project is to design and implement a locking mechanism, which can be unlocked using a passcode via DTMF decoder and all the information being displayed on the 16x2 LCD display, the design was limited to a solenoid actuator as the locking mechanism since this is just a prototype and it was implemented using ATmega328P microcontroller as the project's brain.

Though practically on any passcode lock we use a keypad on for input code, here we are trying on interfacing it with DTMF input through a DTMF decoder since it provides an advantage of being able to literally make a call from any point in the world to unlock this.

And also as future plans we also wish to interface a keyboard on to the setup like in any normal passcode locks. One of the main application is a passcode door lock.

### Objective

The objective is to create a passcode unlockable lock with a display which shows each and every required instructions and the cost of the model is low compared to existing models in the market and also the model consumes less power (other than the locking mechanism) and so it has very relaiable battery backup (due to low power consumption).

## Existing Models

| ![Picture1-removebg-preview](https://github.com/fayizferosh/btech-mini-project/assets/63997454/0afc19cb-3377-4dc8-a8c7-12a1090af355) |
|:--:|
| *Veecome Electronic Digital Number Keypad Password Lock for Cabinet Door Drawer Code Lock **Price: $18.19*** |

| ![61J8-wJ1tZL _SL1001_-removebg-preview](https://github.com/fayizferosh/btech-mini-project/assets/63997454/71bf0bd4-528f-4a44-9c7f-6ec5991c6829) |
|:--:|
| *Zyyini Door Lock, Zinc Alloy Electronic Password Lock Anti-Theft Home Security Door Lock with 2 Mechanical Key **Price: $39.99*** |

| ![electronic-door-lock-250x250-removebg-preview](https://github.com/fayizferosh/btech-mini-project/assets/63997454/ea55ce46-72b9-45cd-ba43-e57ce7f43e26) |
|:--:|
| *Milestone Systems Electronic Door Lock **Price: $184.93*** |

The drawbacks of the existing models are:
* Expensive.
* Lacks display (there are models with display but they are more expensive compared to the models without display we've shown here).
* Consumes too much power (compared to the model we're designing).

The advantages of our model over the existing ones are:
* Cheap compared to the existing models.
* Has a display.
* Low power consumption compared to the existing models.

## Block Diagrams

![Screenshot 2023-09-01 212526](https://github.com/fayizferosh/btech-mini-project/assets/63997454/95ca7eaf-aa7a-45d2-a5dc-31ee2e200eab)

![Picture2](https://github.com/fayizferosh/btech-mini-project/assets/63997454/04d4bdf9-3bac-41d5-a918-42a66459ec07)

### Explanation

The DTMF tone required (i.e., the key that was pressed) is obtained from a mobile phone via an AUX cable to the DTMF decoder module which is connected to the microcontroller. The DTMF decoder module sends this information to the microcontroller where the data is processed and respective commands to display the instructions on the 16x2 LCD display are run. Further, as the user follows the instructions on the LCD display, when the user press the respective key to unlock the microcontroller processes this information and respective commands to activate the relay are run. Since, the solenoid circuit's swictch here is the relay, when the relay is activated, the solenoid is also actuated.

## Components Required

### Hardware Requirements

| Sl No. | Component Name | Quantity |
| ----------- | ----------- | ----------- |
| 1. | MT8870 DTMF Decoder Module | 1 | 
| 2. | 16x2 LCD Display | 1 | 
| 3. | Microcontroller (ATMEGA328P with Uno Bootloader) | 1 |
| 4. | 12V Solenoid Actuator | 1 |
| 5. | 5V Relay Module | 1 |
| 6. | FT232RL USB to UART TTL Module | 1 |
| 7. | Ceramic Capacitor 100nF | 2 |
| 8. | Ceramic Capacitor 22pf | 4 |
| 9. | Crystal Oscillator 16Mhz | 2 |
| 10. | LED 5mm Green | 1 |
| 11. | LED 5mm Red | 1 |
| 12. | T connector for 9V battery | 1 |
| 13. | IC LM7805 | 1 |
| 14. | Jumper Wires | - |
| 15. | Breadboard | 1 |
| 16. | Trimpot 10kΩ | 1 |
| 17. | Adapter 12V DC | 1 |
| 18. | Aux Cable | 1 |
| 19. | Mini USB Cable | 1 |
| 20. | IC Base for ATmega328P | 1 |
| 21. | Resistors 330Ω | 2 |
| 22. | Headstrips for LCD Display | - |
| 23. | 9V Battery | 1 |
| 24. | Rocker Switch | 1 |
| 25. | Push Button | 1 |
| 26. | Breadboard Wire | - |

### Software Requirements

The software used during the course of completion of our project:

#### Fritzing 0.9.3

Fritzing is an open-source initiative to develop amateur or hobby CAD software for the design of electronics hardware, to support designers and artists ready to move from experimenting with a prototype to building a more permanent circuit. We used this for drawing schematic of the circuit and to generate breadboard wiring diagram.

#### Arduino IDE 1.8.13

The open-source Arduino Software (IDE) makes it easy to write code and upload it to the board. This software can be used with any Arduino board. Since we've burned Arduino Uno bootloader to ATmega328P, therefore we use this software itself to write the code.

#### Proteus 8 Professional

The Proteus Design Suite is a proprietary software tool suite used primarily for electronic design automation. The software is used mainly by electronic design engineers and technicians to create schematics and electronic prints for manufacturing printed circuit boards. We used this for simulation of the circuit.

## Circuit Diagram

| ![Design Project_schem](https://github.com/fayizferosh/btech-mini-project/assets/63997454/3b947314-757f-47d0-8674-013202e5d646) |
|:--:|
| *Schematic of the Main Circuit* |

| ![Design-Project-2_bb](https://github.com/fayizferosh/btech-mini-project/assets/63997454/79800dc0-f300-4656-b053-392b63c390a5) |
|:--:|
| *Breadboard Wiring of the Main Circuit* |

| ![Design Project 3_schem](https://github.com/fayizferosh/btech-mini-project/assets/63997454/6950802d-b48d-44ba-a0e5-808f8147f849) |
|:--:|
| *Schematic of the Programming Circuit* |

| ![Design Project 1_bb](https://github.com/fayizferosh/btech-mini-project/assets/63997454/2bf7a51c-abd4-4570-b657-a31bb1335142) |
|:--:|
| *Breadboard Wiring of the Programming Circuit* |

### Design

We chose ATmega328P since we required a microcontroller but we didn't know Assembly Language Programming required to use a microcontroller. We burned Arduino Uno bootloader to the microcontroller so that we could code it using Arduino code which we knew. To use ATmega328P microcontroller as Arduino on breadboard we required just a 16 MHz crystal along with two 22pF ceramic capacitor. But to program we required an extra 100nF ceramic capacitor. All the connections are avalable in schematics above. The reference used for this is in "Reference" section.

We used MT8870 DTMF Decoder Module since it provides information on the key pressed on DTMF keypad a 4-bit code for a key so in total 16 keys. The interfacing, working and further information along with reference to datasheet is available in "Component Study" section.

The 16x2 LCD is very easy to interface with Arduino board, which is the exact reason why we chose it as the display for our project. The interfacing, working and further information along with reference to datasheet is available in "Component Study" section.

The 12V Soleniod was the best component available to us to demonstrate the locking function that we required. Since this is a prototype, as we develop further we will be making significant changes. The interfacing, working and further information along with reference to datasheet is available in "Component Study" section.

For interfacing LEDs we know that both our supply and microcontroller output voltage are 5V and that the forward current of the LED to be 10mA from LED datasheet. So using the equation:

```math
Resistance = \frac{(BatteryVoltage - LEDMinForwardVoltage)}{LEDForwardCurrent}
```

Substituting,

```math
Resistance = \frac{(5V - 2V)}{10mA} = \frac{3V}{10mA} = 300\Omega
```

So, approximately we took 330 $\Omega$ resistor.

Since using relay without proper circuits required might cause back emf voltage spike or some other undesired event, which is the reason why we chose the Relay Module. The circuit consists of a transistor an LED and few resistors. Here the transistor provides protection. A transistor in between will allow a 5V signal from the microconytroller to switch a 12V signal via the transistor to the relay - thus turning it *On*. The LED is connected in such a way that it will be lit when the relay is turned *On*. In the event of a back emf voltage spike or some other undesired event only your transistor will be blown, instead of the entire circuit. The interfacing, working and further information along with reference to datasheet is available in "Component Study" section.

The FT232RL USB to UART TTL Module is the best module available in the market which supports serial programming that is supported by the microcontroller. The interfacing, working and further information along with reference to datasheet is available in "Component Study" section.

## Component Study

### MT8870 DTMF Decoder Module

| ![DTMF-Decoder-Pinout](https://github.com/fayizferosh/btech-mini-project/assets/63997454/37e30048-cf16-408a-8800-ad2d5649943e) |
|:--:|
| *MT8870 DTMF Decoder Module* |

The **MT8870 based DTMF (Dual Tone Multi-Frequency) decoder module** is commonly used to control robots with a mobile phone, it is also used in different kinds of home automation projects where mobile dial pad input is required. This module works as a **tone decoder** that uses its 3.5 mm audio connector socket to get the input audio signal. It is popularly used for mobile and fixed telephone voice dialing and recording related functions.

DTMF is commonly found in tone based dial pad devices such as mobile phones or telephones dial pad. When the dial pad is pressed, it produces a **combination of two separate sine waves** which is a unique frequency signal that can be decoded and produced as a binary output. MT8870 based DTMF module does exactly the same thing. The pressed button can easily be identified by checking the binary output. It can produce binary output by getting tone input from 0-9 number, A - D letters, * and # symbols. The important components on the MT8870 DTMF Module are marked below.

| ![DTMF-Modules](https://github.com/fayizferosh/btech-mini-project/assets/63997454/cb9673f0-4b68-4261-9427-690ce3b5cd71) |
|:--:|
| *Important Components of DTMF Decoder Module* |

The binary output digits are available on the output pin Q1 to the pin Q4. In this module, there are onboard LEDs that can be very useful to identify the output state signal of the binary pins.

The DTMF module has a 3.5 mm audio input Jack that can be easily connected with a mobile phone by using a 3.5mm audio jack. It is very useful to add dual-tone multi-frequency decoding in any microcontroller based projects. The datasheet can be found in "Reference" section.

#### MT8870 DTMF Decoder Module Pinout Description

| Pin Name | Function | Comment |
| ----------- | ----------- | ----------- |
| *Q1* | Binary Bit 1 | LSB | 
| *Q2* | Binary Bit 2 | - | 
| *Q3* | Binary Bit 3 | - |
| *Q4* | Binary Bit 3 | MSB |
| *StQ* | Delayed String Output | Represents Binary Bit 0 - Gives output when a button is pressed |
| $\overline{StQ}$ | Power Down Input | To be grounded |
| *IN* | Inhibit Input | Logic high inhibits the detection of tones representing characters A, B, C and D |
| *VCC* | DC Supply Input | 4.5V - 5.5V (5.0V Nominal) |
| *GND* | Ground | - |

#### DTMF Key Mapping

| Key | IN | StQ | Q4 | Q3 | Q2 | Q1 |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| 1 | - | H | 0 | 0 | 0 | 1 | 
| 2 | - | H | 0 | 0 | 1 | 0 | 
| 3 | - | H | 0 | 0 | 1 | 1 | 
| 4 | - | H | 0 | 1 | 0 | 0 | 
| 5 | - | H | 0 | 1 | 0 | 1 | 
| 6 | - | H | 0 | 1 | 1 | 0 | 
| 7 | - | H | 0 | 1 | 1 | 1 | 
| 8 | - | H | 1 | 0 | 0 | 0 | 
| 9 | - | H | 1 | 0 | 0 | 1 | 
| 0 | - | H | 1 | 0 | 1 | 0 | 
| * | - | H | 1 | 0 | 1 | 1 | 
| # | - | H | 1 | 1 | 0 | 0 | 
| A | L | H | 1 | 1 | 0 | 1 | 
| B | L | H | 1 | 1 | 1 | 0 | 
| C | L | H | 1 | 1 | 1 | 1 | 
| D | L | H | 0 | 0 | 0 | 0 | 
| A | H | L | - | - | - | - | 
| B | H | L | - | - | - | - | 
| C | H | L | - | - | - | - | 
| D | H | L | - | - | - | - |

