# SD-InstallTool_Win_MiSTer
SD Card preparation tool for MiSTer FPGA project: https://github.com/MiSTer-devel/Main_MiSTer/wiki

Latest release link: [1.0.0.0](/releases/20170728/MiSTer%20SD%20Card%20Utility.exe?raw=true)

Supported OS:
- Windows 10 64-bit
- Windows 8.x 64-bit
- Windows 7 64-bit

Not supported:
- Any 32-bit OS (not a technology blocker if there will be a demand, code and builds will be adapted)

Pre-requisites:
- .Net framework v2.0 or newer installed

## Screenshots:

Main window:

![Main window](/doc/screenshots/main.png?raw=true)

Log window:

![Log window](/doc/screenshots/log.png?raw=true)

## Usage:

### Full Install:

Does all the magic automatically. Just insert SD Card (>2GB), click "Full Install" and get things done.

What it does (if you're really interested in):
- Wipe all content on selected SD card
- Create brand bew MBR-base disk
- Re-partition it (3 partitions created: Preloader (Uboot), Linux (Ext4), Data(ExFAT))
- Transfer preloader and linux disk images to correspondent partitions
- Format Data partition with ExFAT system
- [Optional] Copy MiSTer binary and menu files to data partition (if correspondent package available)

### Linux Update:

Available only if SD Card was previously prepared by MiSTer Windows or Linux tools and properly partitioned.

Data partition is not changed. All MiSTer data/cores/configurations stay untouched and safe.

Check for compatibility is done automatically. Button is disable if any pre-condition failed. You can read more details in Log Windows.

Only one action is performed:
- Transfer preloader and linux disk images to correspondent partitions

### Wipe:

Does SD Card wipe operation (MBR and partitioning information cleared up, first 4MB of card wiped with zeroes). So card is now like you just purchased it and contains no information.

Can be useful if you have issues with any SD card that cannot be formatted properly by any device (PC, Mac, DSLR, etc.)

## Notes:
Codebase can be potentially used as a flexible SD card installer/formatter for any other embedded/FPGA/SoC platforms.
