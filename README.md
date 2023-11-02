# OSX-PROXMOX - Run macOS on ANY Computer - AMD & Intel

Install `** FRESH/CLEAN **` Proxmox VE v7.0.XX ~ 8.0.XX - Next, Next & Finish (NNF).

Open Proxmox Web Console -> Datacenter > NAME OF YOUR HOST > Shell.

Copy, paste and execute (code below).

Voilà, install macOS! This is really and magic **easiest way**!
![overview](https://github.com/luchina-gabriel/OSX-PROXMOX/assets/23700365/c86c53f9-cc05-459a-b8dc-b81d90d8ee73)
## COPY & PASTE - in shell of Proxmox (for Install or Update this solution)

```
/bin/bash -c "$(curl -fsSL https://install.osx-proxmox.com)"
```

## For install EFI Package in macOS, first disable Gatekeeper

```
sudo spctl --master-disable
```

## Versions of macOS Supported
* macOS High Sierra - 10.13
* macOS Mojave - 10.14
* macOS Catalina - 10.15
* macOS Big Sur - 11
* macOS Monterey - 12
* macOS Ventura - 13
* macOS Sonoma - 14

## Versions of Proxmox VE Supported
* v7.0.XX ~ 8.0.XX

## Opencore version
* September/2023 - 0.9.5 with SIP Enabled, DMG only signed by Apple and all features of securities.

## Cloud Support (Yes, install your Hackintosh in Cloud Environment)
- [VultR](https://www.vultr.com/?ref=9035565-8H)
- [Vídeo/Tutorial](https://youtu.be/8QsMyL-PNrM), please activate captions!

## Disclaimer

- FOR DEV/STUDENT/TEST ONLY PURPOSES.
- I'm not responsible for any problem and/or equipment damage or loss of files. 
- Always back up everything before any changes to your computer.

## Demonstration (in Portuguese/Brazil)

https://youtu.be/dil6iRWiun0

\* Please use CC with Auto Translate to English for your convenience.

## Credits

- Opencore/Acidanthera Team
- Corpnewt for Applications (ProperTree, genSMBIOS, etc)
- Apple for macOS
- Proxmox - Excelent and better documentation for Virtualization

## Discord - Universo Hackintosh
- [Discord](https://discord.universohackintosh.com.br)

## Fix for Freezing when booting into recovery

On the Host:

Run `dmesg | grep -i -e tsc -e clocksource` and look for the word `unstable`.

If unstable exists then do the following:

Edit your /etc/default/grub file

`sudo nano /etc/default/grub`

Then replace `GRUB_CMDLINE_LINUX_DEFAULT="quiet` with `GRUB_CMDLINE_LINUX_DEFAULT="quiet clocksource=tsc tsc=reliable mitigations=off`

We want to add `clocksource=tsc tsc=reliable mitigations=off` to GRUB_CMDLINE_LINUX_DEFAULT

Lastly on the host, boot into BIOS/UEFI and disable "ErP mode" or any C state power saving modes.

Save your changes, reboot, go back into the BIOS/UEFI, poweroff, unplug the power cable, plug back in, power on.
