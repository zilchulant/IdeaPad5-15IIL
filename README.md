My attempt to get MacOS with OpenCore running on Lenovo IdeaPad 5-15IIL05 (IceLake Notebook with i7-1065G7)

- [1. Status](#1-status)
  - [1.1 Links](#11-links)
  - [1.2 ToDo](#12-todo)
- [3. Hardware](#3-hardware)
  - [3.1 Physical Devices](#31-physical-devices)
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



<br>

# 4. OpenCore