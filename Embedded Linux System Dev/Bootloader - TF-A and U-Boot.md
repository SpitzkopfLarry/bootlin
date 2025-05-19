# Bootloader – TF-A and U-Boot
*Objectives: Set up serial communication, compile and install the U-Boot bootloader, use basic U-Boot commands, set up TFTP communication with the development workstation.*

## Issue
The instructions says you need to run make with the given `DEVICE_TREE`. <br>
`make DEVICE_TREE=stm32mp157a-dk1`
It's very simple to change the `DEVICE_TREE` in Buildroot, but if you set `DEVICE_TREE = stm32mp157f-dk2` it will fail. <br>
The reason for this is, by the the given Buildroot version, this deveopmentboard is no supported yet. <br>
