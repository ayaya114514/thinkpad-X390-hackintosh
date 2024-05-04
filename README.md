# thinkpadX390-hackintosh Sonoma (14.4.1 - OC 0.9.9)

## Table of Contents

- [thinkpadX390-hackintosh Sonoma (14.4.1 - OC 0.9.9)](#thinkpadX390-hackintosh-Sonoma (14.4.1 - OC 0.9.9))
  - [Table of Contents](#table-of-contents)
  - [Device Information](#device-information)
  - [Usage](#usage)
  - [What-is-working](#what-is-working)
    - [Detailed-Device-Drivers](#detailed-device-drivers)
      - [CPU](#cpu)
      - [Battery](#battery)
      - [USB](#usb)
      - [Ethernet](#ethernet)
      - [Display](#display)
      - [Audio](#audio)
      - [Keyboard](#keyboard)
      - [SSD](#ssd)
      - [Bluetooth](#bluetooth)
      - [Trackpad-Trackpoint](#trackpad-trackpoint)
      - [Wireless-Card](#wireless-card)
      - [Integrated-Camera](#integrated-camera)
      - [Thunderbolt 3](#thunderbolt-3)
      - [Headphone/mic combo](#headphonemic-combo)
  - [What-is-not-working](#what-is-not-working)
  - [Recommended-BIOS-Config](#recommended-bios-config)
  - [Tips](#tips)
    - [Hibernation](#hibernation)
  - [Support](#support)
  - [Credits](#credits)

## Device Information
| Specifications | Details |
|:---|:---|
| Computer Model | ThinkPad X390 |
| CPU | Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz |
| Model |  Lenevo 20Q1|
| Displayer | Lenevo LEN4094 ( 13.3 inch  ) |
| Memory | 16 GB ( 2x8 Samsung DDR4 2400 MHz ) |
| NVMe SSD | NVME WD Blue SN570 500GB |
| Integrated Graphics | Intel UHD Graphics 620 (Mobile) |
| Ethernet |  Intel(R) Ethernet Connection (6) I219-V |
| Sound Card | Intel Intel Smart Sound Technology Audio Controller (layout-id: 11) |
| Wireless Card |  Intel(R) Wireless-AC 9560 160MHz |
| I/O |  2xUSB3.1, USB-C Thunderbolt 3, MicroSD card reader, HDMI 1.4, Headphone/mic combo |


## Usage

If you have the same computer as me, you just need to replace your EFI with the EFI in the current directory. Don't forget to update your serial.

## What-is-working

### Detailed-Device-Drivers

#### CPU

Functioning normally. Patched with CPUFriend.kext: 1.6 GHz (Min) - 3.9 GHz(Max)

#### Battery

The power display is functioning normally.

#### USB

USB Ports Patching with USBMap.kext.

#### Ethernet

Functioning normally.

#### Display

The model of Integrated Graphics is `Intel UHD Graphics 620`, faked to `Intel UHD Graphics 630 (Mobile) `.

The HDMI is attached with `Intel UHD Graphics 630` and is functioning normally. `2K@60Hz` & `4K@30Hz` are supported.

#### Audio

Driven by AppleALC with `layout-id: 11`. Everything is working normally. Support Dolby Audio.

#### Keyboard

Functioning normally except the <kbd>Insert</kbd> , which is not presented on Magic Keyboard.

#### SSD

NVMe is functioning normally.

#### Bluetooth

Bluetooth functioning partially (Successfully connected to AirPods but failed on iPhone)

#### Trackpad-Trackpoint

Functioning normally.

#### Wireless-Card

Functioning normally. Wi-Fi speed drops when connected to AirPods.

#### Integrated-Camera

Functioning normally.

#### Thunderbolt 3

Probably functioning normally.

#### Headphone/mic combo

Functioning normally.


## What-is-not-working

- AirPlay, and Continuity Camera fail to work properly, but Handoff works, and Airdrops can achieve one-way transmission from computer to iphone

## Recommended-BIOS-Config

- Security
  - Intel SGX: Software Controlled
- Boot
  - Boot Mode: UEFI Only (CSM Yes) （if the option is not available, please search for a solution on your own）

## Questions-and-Issues

- Airdrops
 - When the Mac OS version is 14.4.1 and iOS version is 17.4, using AirportItlwm can achieve one-way transmission from computer to iphone (I am not sure if higher versions are still applicable, as this feature started with Sonoma 14.4.1)
- warning
 - This efi is only applicable to Sonoma 14.4. If it is lower than this version, AirportItlwm needs to be replaced
- Upgrade
 - If you are using an previous EFI update before Sonoma, please make sure that your Misc Security SecureBootModel is set to Disabled. When the update is completed, you can ignore it or set it to Default
 - When you update the kernel, please make sure to delete the original kernel in the kext folder before proceeding with the update
### Hibernation

Hibernation is supported. No serious issue found after wake-up.

## Support

**Sonoma**
- 14.4.1

## Credits
- [@mahronid](https://github.com/mahronid) for [thinkpad-x390-hackintosh](https://github.com/mahronid/thinkpad-x390-hackintosh)
- [@mendax1234](https://github.com/mendax1234) for [ThinkpadX390-Opencore-EFI](https://github.com/mendax1234/ThinkpadX390-Opencore-EFI)
- [@VGEAREN](https://github.com/VGEAREN) for [Lenovo-X390-Big-Sur-OC-EFI](https://github.com/VGEAREN/Lenovo-X390-Big-Sur-OC-EFI)
- [@bayukp](https://github.com/bayukp) for [Thinkpad-X390-Opencore](https://github.com/bayukp/Thinkpad-X390-Opencore)
