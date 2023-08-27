# ASUS FA-706IH Laptop Hackintosh

[![MacOS version](https://img.shields.io/badge/Ventura-13.5.1-informational.svg)](https://www.apple.com/macos) [![OpenCore version](https://img.shields.io/badge/OpenCore-0.9.4-informational.svg)](https://github.com/acidanthera/OpenCorePkg)

![HacOS Ventura](https://github.com/Ragnarok93/ASUS-F17-Ryzentosh/blob/main/Screenshot%202023-08-26.png?raw=true)

## DISCLAIMER:
Use at your own risk. I am not liable for any damage you may cause to your own hardware or data loss.

## Specifications

| Component      | Model                               |
|----------------|-------------------------------------|  
|CPU             | AMD Ryzen 5 4600H                   |
|iGPU            | 2Gb Radeon Graphics                 |
|dGPU            | Nvidia GTX 1650 (Disabled)          |
|Ethernet        | Realtek 8111/8168/8411              |
|OS Disk         | Micron 2210 512Gb SSD + Seagate ST1000lm035 1Tb HDD    |
|RAM             | 16Gb 2667mHz                        |

## What's Working

* CPU Power Management (Use AMD Power Management for better control of Power States)
* Integrated Graphics Acceleration (Known issue of graphical glitches on chromium based browsers when Hardware Acceleration Enabled in browser settings)
* HDMI Output (No audio over HDMI at the moment)
* Keyboard & Function Keys, including: Volume, Display Brightness, Sleep
* Trackpad with multi-touch & Gestures
* Ethernet
* All USB Ports
* Webcam 
* Sleep & Wake
* iServices like iCloud, iMessage, Facetime
* DRM
* Battery Management

## What's Not Working Currently

* Wifi/Bluetooth - Realtek 8822CE is unsupported, use a supported PCIe card instead and the corresponding kexts for functionality.
* Keyboard Backlight 
* Microphone

| Drivers                | Kexts                      | SSDTs               | Patchers, etc              |
|------------------------|----------------------------|---------------------|----------------------------|
|AudioDxe                |AMDRyzenCPUPowerManagement  |SSDT-ALS0            | SSDTtime                   |
|OpenHfsPlus             |AmdTscSync                  |SSDT-dGPU-Off        | AMD Vanilla Patches        |
|OpenCanopy              |AppleALC                    |SSDT-EC              | CPU-Name Tool              |
|OpenRuntime             |AppleMCEReportDisabler      |SSDT-HPET            | SmokelessUMAF for 2Gb VRAM |
|OpenVariableRuntimeDxe  |AsusSMC(?)                  |SSDT-PLUG-ALT        | GenSMBIOS                  |
|ResetNvramEntry         |BrightnessKeys              |SSDT-USBX            | Dreams in Verbose          |
|                        |ECEnabler                   |SSDT-USBX            | 3 Days of Troubleshooting  |
|                        |GenericUSBXHCI              |SSDT-XOSI            | 4+ Pots of Coffee          |
|                        |HoRNDIS                     |                     | A large part of my sanity  |
|                        |Lilu                        |                     |                            | 
|                        |NootedRed                   |                     |                            |
|                        |RadeonSensor                |                     |                            |
|                        |RealtekRTL8111              |                     |                            |
|                        |RestrictEvents              |                     |                            |
|                        |SMCAMDProcessor             |                     |                            |
|                        |SMCBatteryManager           |                     |                            |
|                        |SMCLightSensor              |                     |                            |
|                        |SMCRadeonGPU                |                     |                            |
|                        |SMCSuperIO                  |                     |                            |
|                        |USBToolbox/UTBMap           |                     |                            |
|                        |VirtualSMC                  |                     |                            |
|                        |VoodooI2C                   |                     |                            |
|                        |VoodooI2CHID                |                     |                            |

## Bootloader
Installed alongside Windows 11, using OpenCore as my Bootloader & OpenCanopy for GUI.

*Note about booting MacOS - to get past the prohibitory symbol I had to place OpenVariableRuntimeDxe.efi BEFORE OpenRuntime.efi in the Config.plist with LoadEarly set to True. If using ProperTree and the OC Clean Snapshot function it will place them in the wrong order and reset the LoadEarly value every time.

![OpenCanopy Picker](https://github.com/Ragnarok93/ASUS-F17-Ryzentosh/blob/main/Picker.png?raw=true)

## Credits & Links
* [OpenCore install guide](https://dortania.github.io/OpenCore-Install-Guide)
* [NootedRed](https://nootinc.github.io/)
* [TonyMacx86 Forum Posts](https://www.tonymacx86.com/)
* [EliteMacx86 Forum Posts](https://elitemacx86.com/)
* All the talented people that contribute to make these kinds of projects possible! 





