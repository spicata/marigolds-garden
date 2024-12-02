---
title: Computer Buses
---

#saplings 

- A bus is a communications system
- Buses are a set of physical connections such as cable and circuits that can be shared by multiple hardware components.
	- Memory and IO devices are connected to the CPU through buses
	- A bus contains multiple wires. Each wire carries one or more bits. More wires means more memory that a bus can carry.
- 3 types: address, data, control
- Address bus is unidirectional (CPU -> device) and it is used to identify particular locations in memory
	- Transports address that computer wants to read or write
	- Size of address bus determines how many unique locations can be addressed
		- e.g. 4-bit address bus = 2^4 bits of memory
- Data buses are bidirectional and they transfer data
- Control buses are bidirectional and they carry control data, such as orders, sync data, or response signals
- Buses operate at certain frequencies e.g. 200 MHz. This is the bus width
- Buses are either parallel/serial or internal(local)/external(expansion)
	- Internal buses allow communication between internal components, such as memory. External buses allow communication with peripherals, like with USBs.
	- Parallel buses can transmit several bits at a time. Serial buses can only transmit one.
- Address bus contains the memory address. Data bus contains the data. Control bus sends commands.
- Common buses: eSATA/SATA (disks), USB (peripherals), Thunderbolt (USB-C peripherals), PCIe
- USB is a Universal Serial Bus
