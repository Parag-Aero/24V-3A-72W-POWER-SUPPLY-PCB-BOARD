# 24V 3A 72W POWER SUPPLY PCB BOARD

## Overview

This PCB was designed to provide a regulated **24V DC power supply** for driving **775 DC motors**, actuators, and other 24V loads. The board is designed for a maximum rated output current of **3A** and has been successfully fabricated and tested.

## Working Principle

The PCB is designed to be powered using a 12-0-12V center-tapped transformer. However, the center-tap connection is not used in this design. Only the two outer secondary terminals of the transformer are connected to the PCB.

After rectification and filtering, the resulting DC voltage is typically around 30V DC.The Typical DC Input to Regulator is Approximately 28V–34V DC (depending on transformer and operating conditions)

The design uses an **LM7824 voltage regulator** to generate a regulated 24V output rail. Since the LM7824 can supply a maximum current of only **1.5A**, a **2N3055 power transistor** is connected as a current bypass/pass transistor.

The transistor carries most of the load current, while the LM7824 provides voltage regulation and only a small portion of the total current. This arrangement allows the power supply to deliver up to **3A continuously**.

### Output Voltage

During testing, an approximate **0.5V voltage drop** was observed across the 2N3055 transistor. As a result, the measured output voltage is approximately:

* Expected output: 24V
* Actual output: ~23.5V

## Current Handling Capability

* Design output current: **3A**
* PCB trace capability: **Up to 5A continuous**
* Excess capability above design rating: **2A**

Although the PCB itself can handle up to 5A continuously, operating above the intended 3A rating may cause excessive heating of the transformer, potentially leading to reduced lifespan or failure.

## Cooling Requirements

**Important:** Proper heat dissipation is required for reliable operation.

Attach suitable heat sinks to:

* LM7824 voltage regulator
* 2N3055 power transistor

Failure to use adequate heat sinks may result in overheating and damage to the components.

## Assembly Notes

### External Connections

1. Solder one **2-pin JST-XH connector** to the SPST power switch.
2. Solder another **2-pin JST-XH connector** to the power indicator LED.

### Enclosure

A custom enclosure may be designed and 3D printed or fabricated to house:

* The PCB
* SPST power switch
* Power indicator LED

This will improve safety, durability, and overall appearance.

## Design Status

| Item       | Status                                                                                      |
| ---------- | ------------------------------------------------------------------------------------------- |
| Fabricated | Yes                                                                                         |
| Tested     | Yes                                                                                         |
| Functional | Yes                                                                                         |
| DRC Check  | Contains footprint-related clearance violations originating from imported vendor footprints |

## Repository Contents

This repository includes:

* Complete EasyEDA source files
* PCB design files
* Component list
* Single-layer PCB printing documents

The provided PCB printing files can be used directly for fabrication methods such as:

* Toner transfer
* Photoresist processing
* Other single-layer PCB manufacturing techniques

## Disclaimer

This design has been tested and verified as functional. However, users should ensure proper transformer sizing, adequate cooling, and safe assembly practices before operating the board under high-current conditions.
