
<img width="2339" height="1653" alt="system-bloc-photon-drive-1" src="https://github.com/user-attachments/assets/eb85de5a-d365-426f-8ae6-19bb1c070585" />

# Project Overview

This project is an experimental horticultural lighting platform developed to study how precise spectral control can influence plant growth.

The project compares **targeted-spectrum LED lighting** with more traditional fixed-spectrum approaches. Its main objective is to determine whether dynamically controlled light can support crop steering and enable lighting recipes that evolve throughout the different stages of a grow cycle.

## Project Objectives

* Compare targeted spectral lighting with conventional horticultural lighting.
* Independently control multiple spectral channels.
* Develop light recipes that change over time and according to plant growth stages.
* Measure the interaction between artificial lighting and ambient light.
* Evaluate energy use, plant response, consistency and practical system performance.
* Document experimental results against a conventional lighting reference.

## Custom Electronics

The platform is built around custom electronic hardware designed specifically for modular horticultural lighting.

The main driver board handles power regulation, channel control, sensing and communication. Each spectral channel can be controlled independently, allowing the system to adjust both total light output and spectral composition.

<img width="1723" height="1022" alt="EG60C4 Render" src="https://github.com/user-attachments/assets/b28c42f4-d03e-45be-8550-de1af1d68f36" />





[EG60C4 Schematic.pdf](https://github.com/user-attachments/files/30069281/EG60C4.Schematic.pdf)




The LED tiles are also custom-designed. Each tile integrates multiple LED spectra on an aluminum-core PCB to improve thermal transfer and create a compact, modular light source.

<img width="1723" height="1022" alt="EG50TL Render" src="https://github.com/user-attachments/assets/64289ebe-c966-4bc6-b3bf-6ef162107f5f" />



## Modular Architecture

A complete system consists of:

* One AC-to-DC power supply.
* One four-channel electronic driver board.
* Two to four modular LED tiles.
* Independent thermal management for each tile.
* Light-intensity and spectral sensing.
* Embedded control and data logging.

This architecture allows the system to scale from approximately **100 W to 200 W** while keeping the same control platform.

## Research Direction

The long-term goal is to determine whether closed-loop spectral control can:

* Maintain consistent lighting conditions despite changes in ambient light.
* Improve electrical efficiency.
* Support repeatable crop-steering strategies.
* Produce practical light recipes for different crops and growth stages.
* Provide measurable advantages over conventional lighting systems.

The platform will be tested alongside conventional horticultural lighting to create a practical reference for power consumption, light output, plant response and overall system performance.

---

## Electronics Development

This project is built around custom electronic assemblies developed specifically for modular, multi-channel horticultural lighting.

The electronics are divided into two main subsystems:

* A central driver board responsible for power conversion, LED current regulation, sensing and embedded control.
* Modular aluminum LED tiles containing the different spectral channels.

The project documents the complete electronics-development process, including component selection, schematic design, PCB layout, prototyping, design-for-manufacturing decisions and PCBA validation.


<img width="2200" height="1700" alt="EG60C4 Schematic-1" src="https://github.com/user-attachments/assets/b9187d40-3e15-4a7a-9dd9-365ae263e154" />

[EG60C4 Schematic.pdf](https://github.com/user-attachments/files/30069281/EG60C4.Schematic.pdf)


---

## LED Current Drivers — TPS92515HV

Each spectral channel is controlled by a dedicated TPS92515HV constant-current buck driver.

This architecture allows the current of each LED string to be regulated independently. Separate channels can therefore be assigned to different wavelength groups, such as white, deep blue, hyper red and far red.

The driver stages are designed around:

* Independent current regulation for each spectral channel.
* Analog dimming through the external DAC.
* PWM control from the microcontroller.
* High-voltage input compatibility.
* Efficient switching operation.
* Compact current-sense and power-loop layout.
* Scalable connection to multiple LED tiles.

Particular attention is given to the switching-current path, current-sense routing, thermal dissipation and placement of the input, output and timing components.

<img width="1419" height="847" alt="LED Current Drivers — TPS92515HV" src="https://github.com/user-attachments/assets/7b40067d-a884-43ba-b042-16aab6790c41" />


---

## 3V3 Power Supply — LMR38020

The embedded control electronics are powered by an LMR38020 step-down converter.

This stage converts the main DC input into a regulated 3.3 V supply for the microcontroller, DAC, sensors and supporting logic.

The design focuses on:

* Operation from the main system power rail.
* Efficient conversion to 3.3 V.
* Low output ripple.
* Sufficient transient response for wireless communication and digital loads.
* Appropriate input and output capacitor selection.
* Compact switching-loop geometry.
* Clear separation between the power-conversion area and sensitive analog circuitry.

The layout of the regulator is treated as a critical part of its design. The high-current switching loop is kept short, while the feedback network is routed away from noisy switching nodes.


<img width="1070" height="799" alt="3V3 Power Supply — LMR38020" src="https://github.com/user-attachments/assets/78da4ed4-a386-4c54-a049-a0de7f1c9a29" />


---

## Embedded Controller — ESP32-C6

An ESP32-C6 module acts as the central controller of the lighting platform.

The microcontroller manages:

* LED-channel PWM signals.
* Communication with the DAC and external sensors.
* Lighting schedules and spectral recipes.
* Closed-loop control algorithms.
* Data acquisition and logging.
* USB programming and diagnostics.
* Wireless communication and future network integration.

The ESP32-C6 was selected to provide a flexible embedded platform with sufficient communication interfaces, processing capability and software support for continued experimentation.

The board exposes selected GPIO, communication and test signals to simplify firmware development, troubleshooting and future hardware expansion.


<img width="1367" height="853" alt="Embedded Controller — ESP32-C6" src="https://github.com/user-attachments/assets/56361452-e799-4328-bd17-60848280decc" />

---

## Analog Current Control — MCP4728 DAC

An MCP4728 four-channel digital-to-analog converter generates the analog reference signals used by the LED-driver stages.

Each DAC output corresponds to one lighting channel, allowing the firmware to adjust the current of each spectral group independently.

This approach provides:

* Four independently programmable analog outputs.
* Fine current adjustment beyond basic PWM dimming.
* Repeatable channel settings.
* Software-defined spectral ratios.
* Gradual transitions between lighting recipes.
* Calibration capability for component tolerances and LED variations.

The DAC works alongside PWM control, allowing the system to combine precise current limits with dynamic dimming and timing control.


<img width="1127" height="633" alt="Analog Current Control — MCP4728 DAC" src="https://github.com/user-attachments/assets/9834f170-213b-4afc-9f29-87b59a537220" />

---

## Connector Selection and Modularity

Connector selection is an important part of the modular system architecture.

The connectors must carry LED current reliably while remaining compact, serviceable and resistant to accidental disconnection. Separate connections may also be required for power, control signals, sensors, programming and debugging.

Connector decisions consider:

* Current and voltage ratings.
* Contact resistance.
* Mechanical retention.
* Polarization and keying.
* Cable availability.
* Assembly simplicity.
* Serviceability.
* PCB footprint size.
* Compatibility with repeated connection cycles.
* Suitability for professional cable-harness assembly.

The goal is to use connectors that support rapid prototyping without compromising the reliability expected from a future product-oriented design.

---

## Thermal Design

Thermal performance is central to both the electrical design and the horticultural application.

The LED tiles use aluminum-core PCBs to conduct heat away from the LED packages and into dedicated heatsinks. The objective is to remove heat through the rear mechanical structure rather than allowing it to accumulate around the plant canopy.

The thermal design considers:

* LED junction-to-board thermal paths.
* Electrically isolated thermal pads.
* Copper distribution beneath and around the LEDs.
* Aluminum-core PCB dielectric thickness and thermal conductivity.
* Mechanical contact between the tile and heatsink.
* Thermal-interface materials.
* Heatsink surface area and orientation.
* Driver and regulator component temperatures.
* Temperature monitoring and protective control strategies.

Thermal behavior will be evaluated under different power levels, tile configurations and airflow conditions.

---

## Design for Manufacturing

The PCB assemblies are designed with manufacturing constraints considered from the beginning of the development process.

Design-for-manufacturing work includes:

* Standardized component packages where practical.
* Component availability and sourcing risk.
* Pick-and-place compatibility.
* Appropriate courtyard and assembly clearances.
* Manufacturer-supported trace, spacing, drill and via dimensions.
* Solder-mask and paste-mask design.
* Thermal-pad and exposed-pad assembly requirements.
* Test-point accessibility.
* Connector mechanical support.
* Consistent component orientation.
* Panelization and board-edge constraints.
* Clear silkscreen markings for assembly and troubleshooting.

These decisions are intended to reduce assembly risk, improve repeatability and make future revisions easier to manufacture at larger quantities.

---

## PCBA and Prototype Manufacturing

Prototype boards are manufactured and assembled using a professional PCB and PCBA service.

The process includes:

1. Schematic verification and electrical-rule checking.
2. PCB layout and design-rule checking.
3. Generation of Gerber, drill and fabrication files.
4. Preparation of the bill of materials.
5. Generation of component-placement files.
6. Manufacturer design-for-manufacturing review.
7. PCB fabrication.
8. Automated component assembly.
9. Visual inspection and electrical testing.
10. Manual assembly of connectors, modules or unsupported components.
11. Firmware programming and functional validation.

Using a PCBA service allows the project to evaluate production-oriented component selection, assembly tolerances and manufacturing documentation while still operating at prototype quantities.

---

## Validation and Iteration

Each hardware revision will be tested before being integrated into the complete lighting platform.

Validation will include:

* Power-rail verification.
* LED-current accuracy.
* Channel-to-channel consistency.
* PWM and analog-dimming response.
* Converter efficiency.
* Switching-waveform inspection.
* Thermal measurements.
* Communication-interface testing.
* Sensor integration.
* Fault-condition testing.
* Long-duration operation.

The results of each revision will be documented and used to guide the next schematic, PCB and firmware iteration.

