
[EG60C4 Schematic.pdf](https://github.com/user-attachments/files/30069184/EG60C4.Schematic.pdf)
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

<img width="949" height="933" alt="EG60C4 Layers" src="https://github.com/user-attachments/assets/6113da15-f3c3-4a40-b144-6c9cfb4e13ef" />

![Driver board electrical schematic](docs/images/driver-board-schematic.png)

[View the complete driver board schematic](docs/schematics/driver-board-schematic.pdf)



<img width="2200" height="1700" alt="EG60C4 Schematic-1" src="https://github.com/user-attachments/assets/b9187d40-3e15-4a7a-9dd9-365ae263e154" />


[EG60C4 Schematic.pdf](https://github.com/user-attachments/files/30069281/EG60C4.Schematic.pdf)


The LED tiles are also custom-designed. Each tile integrates multiple LED spectra on an aluminum-core PCB to improve thermal transfer and create a compact, modular light source.

<img width="1723" height="1022" alt="EG50TL Render" src="https://github.com/user-attachments/assets/64289ebe-c966-4bc6-b3bf-6ef162107f5f" />

![LED tile electrical schematic](docs/images/led-tile-schematic.png)
<img width="948" height="926" alt="EG50TL Layers" src="https://github.com/user-attachments/assets/8e632e75-9b7b-40ec-a6ba-f30e5febf76f" />

[View the complete LED tile schematic](docs/schematics/led-tile-schematic.pdf)


<img width="2200" height="1700" alt="EG50TL Schematic-1" src="https://github.com/user-attachments/assets/87e844ac-4e90-4d9f-afeb-8d97374bd1bc" />

  [EG50TL Schematic.pdf](https://github.com/user-attachments/files/30069267/EG50TL.Schematic.pdf)

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

Photon is not presented as a finished commercial grow light. It is an evolving research and development platform used to test lighting strategies, hardware configurations and control algorithms.

The long-term goal is to determine whether closed-loop spectral control can:

* Maintain consistent lighting conditions despite changes in ambient light.
* Improve electrical efficiency.
* Support repeatable crop-steering strategies.
* Produce practical light recipes for different crops and growth stages.
* Provide measurable advantages over conventional lighting systems.

All hardware revisions, electrical schematics, software, test procedures and experimental results will be documented in this repository.
