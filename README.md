My attempt to get MacOS with OpenCore running on Lenovo IdeaPad 5-15IIL05 (IceLake Notebook with i7-1065G7)

- [1. Status](#1-status)
  - [1.1 Links](#11-links)
  - [1.2 ToDo](#12-todo)
- [3. Hardware](#3-hardware)
  - [3.1 Physical Devices](#31-physical-devices)
  - [3.2 Connection of devices:](#32-connection-of-devices)
  - [3.3 USB Ports:](#33-usb-ports)
- [4. OpenCore](#4-opencore)

<br>

---

<br>

# 1. Status

Current status of OpenCore:

<br>

## 1.1 Links


- [Lenovo Support](https://pcsupport.lenovo.com/de/de/products/laptops-and-netbooks/5-series/5-15iil05/downloads/driver-list)
- [Lenovo PSREF](https://psref.lenovo.com/Detail/IdeaPad/IdeaPad_5_15IIL05?M=81YK003EGE)
- [Lenovo Replacement Parts](https://pcsupport.lenovo.com/de/de/products/laptops-and-netbooks/5-series/5-15iil05/81yk/parts/display/compatible)

<br>

- [Dortania OC Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [Dortania OC ACPI Guide](https://dortania.github.io/Getting-Started-With-ACPI/)
- [Dortania OC Post-Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [ANYmacOS](https://www.sl-soft.de/anymacos/)
- [Kext Updater](https://www.sl-soft.de/kext-updater/)
- [Hackintool](https://github.com/headkaze/Hackintool/releases)
- [MaciASL](https://github.com/acidanthera/MaciASL/releases/)
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [IORegistryExplorer](https://github.com/vulgo/IORegistryExplorer/releases)
- [SSDTTime](https://github.com/corpnewt/SSDTTime)
- [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases)

<br>

## 1.2 ToDo

-  :white_large_square: Standby is not working at all
-  :white_large_square: Keyboard Backlight is not turning off when closing the lid
-  :white_large_square: HDMI-Out ends in Kernel Panik
   -  Should be fixed when audio is disabled for HDMI with `set "No-hda-gfx" to "onboard-1" in audio device properties`
-  :white_large_square: USB-C HDMI out ends in Kernel Panik
   -  Should be fixed when audio is disabled for HDMI with `set "No-hda-gfx" to "onboard-1" in audio device properties`
-  :white_large_square: Microphones are not working
   -  might be an issue as Hardware is an Intel Smart Sound Microphone array

<br>

# 3. Hardware

## 3.1 Physical Devices

|Part|Brand|Model|Notes|
|:--|:--|:--|:--|
|**Notebook**|Lenovo|**IdeaPad5-15IIL05**|might internationally be known as S550|
|CPU|Intel|i7-1065G7||
|RAM||16GB|soldered|
|iGPU|Intel|Iris Pro Plus G7|*ID: 0x8A52*|
|dGPU|Nvidia|MX350|disabled via SSDT|
|SSD|WD|PC SN730, 512GB|Windows, Ubuntu, MacOS|
|Audio|Realtek|ALC257|alcid= 11 or other? |
|Microphon|Intel|Smart Sound Microphonearray|recognised, but does not work|
|Trackpad||Microsoft HID Precission Touchpad|MSFT0001|
|Wifi|Intel|AX201 (2x2)| |
|Bluetooth|Intel|Version 5.1||
|HDMI||Version 1.4b|||

<br>

## 3.2 Connection of devices:

ACPI Paths

|Device|Path|Note|
|:--|:--|:--|
|Keyboard|\_SB.PCIO.LPCB.PS2K|PS2|
|Trackpad|\_SB.PCIO.I2C1.TPD0||
|iGPU|\_SB.PCIO.GFX0||
|GPU|\_sb.PCIO.RP05.PXSX||
|400 Chipset|\_SB.PCIO.SAT0||
|Camera|\_SB.PCIO.XHC.RHUB.HS05.CAMA|USB Connected|
|USB-Controller|\_SB.UBTC|Might be CPU integrated TB|
|USB 3.1 Controller|\_SB.PCIO.XHC||
|Intel SMBus|\_SB.PCIO.SBUS|34A3|

<br>

## 3.3 USB Ports:



<br>

# 4. OpenCore