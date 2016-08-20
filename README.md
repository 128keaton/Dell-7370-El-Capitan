# Dell-7370-El-Capitan

## Updates:
20-8-16: Initial Posting

## Specs:
* CPU: Intel m5 6Y57
* GPU: Intel HD 515 Graphics
* Audio: unknown
* WiFi: Intel Dual-band AC-8260 - BCM94352Z is a [work in progress](http://www.tonymacx86.com/threads/bcm94352z-causing-kernel-panics.200102/#post-1308170)

## Notes:
* `platform-id` for the GPU (after increasing the preallocated-DVMT): `0x191e0000`
* WiFi does not and will not work in the forseeable future.

## Kexts:
  - [FakePCIID](https://bitbucket.org/RehabMan/os-x-fake-pci-id/downloads)
    - FakePCIID_Intel_HD_Graphics
    - FakePCIID
  - ACPIBatteryManager
  - ApplePS2Controller
  - IOAHCISerialATAPI_Injector
  - USBInjectAll
  
## Prerequisites:
  1. Increase the preallocated-DVMT:
    - [Guide](https://www.firewolf.science/2015/04/guide-intel-hd-graphics-5500-on-os-x-yosemite-10-10-3/)
    - Note: I am not responsible if I break your machine, but the command I ran (matching the specs above) was just `setup_var 0x432 0x3`
  
