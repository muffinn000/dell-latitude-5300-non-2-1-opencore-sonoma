# dell-latitude-5300-non-2-1-opencore-sonoma

# OpenCore Configuration for Dell Latitude 5300 (macOS Sonoma Supported)

This repository contains the OpenCore configuration for the Dell Latitude 5300 laptop. The goal is to create a stable and functional macOS installation on this device.

![Dell Latitude 5300 macOS Screenshot](https://i.imgur.com/lt2A9JE.png)

---

## Device Specifications

- **Model**: Dell Latitude 5300
- **Processor**: Intel Core i5 8265u
- **Graphics**: Intel UHD Graphics 620
- **Memory**: DDR4 16 GB
- **Storage**: SSD Samsung SSD EVO 860 1TB
- **Network Card**: Intel 9560

---

## macOS Compatibility

The current configuration supports the following macOS versions:
- macOS Sonoma (14.x)
- macOS Ventura (13.x)
- macOS Monterey (12.x)
- macOS Big Sur (11.x)

---

## Supported Features

- [x] Graphics (Intel UHD Graphics 620)
- [x] Wi-Fi (requires replacement or usage of Intel kexts)
- [x] Bluetooth
- [x] Audio
- [x] Battery and power management
- [x] Sleep mode
- [x] Trackpad and keyboard
- [x] USB ports
- [x] HDMI/DisplayPort

---

## Installation

### 1. Prepare the USB Installer
1. Download the macOS image from the [Dortania OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/).
2. Follow the instructions on the same page to create a bootable USB installer using `createinstallmedia` or other tools, as described.

### 2. Configure OpenCore
1. Copy the `EFI` folder from this repository to the EFI partition of your USB installer.
2. Edit the `config.plist` file using [ProperTree](https://github.com/corpnewt/ProperTree) or another editor.

### 3. BIOS Settings
- Disable `Secure Boot`.
- Enable `UEFI Boot`.
- Disable `VT-d` (unless using the `DisableIoMapper` kext).
- Disable `CFG Lock` (or use a patch to bypass it).
- Enable `XHCI Hand-off`.

### 4. Install macOS
1. Boot from the USB installer with OpenCore.
2. Follow the standard macOS installation instructions.

## Included Kexts

- **Lilu.kext**: Core library for patches.
- **WhateverGreen.kext**: Graphics patches.
- **AppleALC.kext**: Audio support.
- **VirtualSMC.kext**: SMC emulation.
- **IntelMausi.kext**: Ethernet support.
- **AirportItlwm.kext**: Wi-Fi support for Intel cards.
- **VoodooPS2Controller.kext**: Trackpad and keyboard support.

## Known Issues and Limitations

- **iMessage/Facetime**: Requires proper SMBIOS setup.

## Credits

- [Acidanthera](https://github.com/acidanthera) for OpenCore and kexts.
- The [Hackintosh](https://www.tonymacx86.com/) community for support and documentation.


