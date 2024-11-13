## Radiation Setup Helpers

This GitHub repository contains tools for performing radiation tests on electronic devices. 
The scripts provided are designed to be used together, as illustrated in the diagram below.

For setups where the **Device Under Test (DUT)** resembles an **embedded device** with limited interfaces (like UART) 
rather than a fully capable Linux machine, refer to the [radhelper-embedded](https://github.com/radhelper/radhelper-embedded) repository.

A **main server** will be located outside the beam room, connected via a local network. 
This server will run the [radiation-setup](https://github.com/radhelper/radiation-setup) scripts.
These scripts control the operations of host devices inside the beam room and act as a watchdog 
for the applications and operating systems within the beam room.
In case of a functional interruption of a host device, the **main server** will use Ethernet-controlled power switches
to perform a hard power cycle of the host devices.

In most setups, the **host devices** inside the beam room are positioned outside the main **beam line**. 
These host devices will run code built/linked with [libLogHelper](https://github.com/radhelper/libLogHelper). 
This library does the communication with the **main server** by sending heartbeat messages. 
The **DUTs** are the devices being tested. 
Any events involving the DUTs should be logged either on the host devices, on the server, or both.

![RadHelper tools usage](https://github.com/radhelper/.github/blob/main/profile/radhelper_overview_dark.jpg#gh-dark-mode-only)
![RadHelper tools usage](https://github.com/radhelper/.github/blob/main/profile/radhelper_overview_light.jpg#gh-light-mode-only)

## Participating institutions

![Institutions](https://github.com/radhelper/.github/blob/main/profile/inst.jpg)

