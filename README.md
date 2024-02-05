## Hackintosh for Asus Vivobook X512DA/AMD Ryzen 5 3500u
Working EFI for Asus VivoBook X512DA running on AMD ryzen 5 3500 (AMD Radeon Vega 8 Graphics).

### Working Features

- Wifi/Bluetooth
- Audio 
- All USB Ports
- Touchpad
- Keyboard
- Ethernet
- HDMI
- ScreenCast/Air Play
- Apple ID
- Brightness Control
- Battery Status
- Graphics Acceleration (Using NootedRed.kext)
- Sleep/Wake

### Steps

1. Download the desired Mac version by following the steps in the [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html). (Screen Cast works only on Monterey and below)
2. Download the EFI folder attached to this repo.
3. Use SSDTTime to dump your DSDT.aml file and copy it to `EFI/OC/ACPI` and replace.
4. Copy the `com.apple.recovery.boot` along with the `EFI` folder to a FAT32 formatted partition or pendrive.
5. Boot the system and select boot from the created pendrive/partition.
6. Once Mac OS Recovery is booted, connect Wi-Fi first, then select Disk Utility and Format a partition in APFS type.
7. Now use Re-install option and continue with the installation.
8. Multiple reboots may happen towards the end, select Mac OS installer during bootups. (If the boot hangs up, force reboot by long pressing the power button)

### Fixing Sleep/Wake properly

1. Edit DSDT and change `_PWR` values by following the guide [here](https://github.com/grvsh02/A-guide-to-completely-fix-sleep-wake-issues-on-hackintosh-laptops/blob/main/README.md).
2. For flawless Sleep Wake functionality, go to the `/Library/Preferences/` directory and delete any files with the name of `com.apple.PowerManagement` using Terminal.
The files would regenerate after a reboot, and you should be good.

3. Additionally, you can try turning off standby using Hackintool if you are facing reboots on long sleeps.

