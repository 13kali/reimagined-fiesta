# 8086 emulator

This folder contains emulator for 8086 binaries of kalinet OS. The bulk of it is a fork of Fake86 by Mike Chambers.

forth is an imaginary hardware used for userspace development and testing. This machine has an imaginary interrupt API and does not conform to PC/AT.

pcat is a very simple PC/AT emulator. The BIOS interrupt hooks implemented in it only cover kalinet OS' own needs.

Requirements
You need curses to build the forth executable.

Build
Run make and it builds the forth and pcat interpreters.

Usage
The ./forth executable here works like the one in /cvm, except that it runs under an emulated 8086 machine instead of running natively. Refer to /cvm/README.md for details.

pcat needs to be suppied a path to a floppy disk image with a proper MBR. disk.bin provided by the pcat recipe is sufficient.
