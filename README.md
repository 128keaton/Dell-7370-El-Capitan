# Dell-7370-El-Capitan

## Updates:
21-8-16: Added more kexts, WiFi and Audio Updates
20-8-16: Initial Posting

## Specs:
* CPU: Intel m5 6Y57
* GPU: Intel HD 515 Graphics
* Audio: ALC3246 - ALC256
* WiFi: Intel Dual-band AC-8260 - BCM94352Z is a drop-in replacement (the `config.plist` supplied has pre-applied patches)

## Prerequisites:
  1. Increase the preallocated-DVMT:
    - [Guide](https://www.firewolf.science/2015/04/guide-intel-hd-graphics-5500-on-os-x-yosemite-10-10-3/)
    - Note: I am not responsible if I break your machine, but the command I ran (matching the specs above) was just `setup_var 0x432 0x3`
    

## Notes:
* `platform-id` for the GPU (after increasing the preallocated-DVMT): `0x191e0000`
* WiFi does not and will not work in the forseeable future.
* 10.11.4+ only, due to lack of Skylake support on previous versions.
* `config.plist` contains Handoff/Continuity/5GHz WiFi patches for the BCM94352Z

## Kexts:
Place in /Library/Extensions, run:

`sudo chmod -Rf 755 /L*/E* && chown -Rf 0:0 /L*/E* && sudo touch -f /L*/E*`
 
- ### Remote Download:
  
    - [FakePCIID](https://bitbucket.org/RehabMan/os-x-fake-pci-id/downloads)
     - FakePCIID_Intel_HD_Graphics
     - FakePCIID_Broadcom_WiFi
     - FakePCIID
  
    - [BrcmPatch](https://bitbucket.org/RehabMan/os-x-brcmpatchram/downloads) <- for BCM94352Z
      - BrcmFirmwareData
      - BrcmFirmwareRepo
      - BrcmPatchRAM2
  
- ### [Repository Pack](https://github.com/128keaton/Dell-7370-El-Capitan/blob/master/kexts.zip):
    - *Kexts Included:*
     - ACPIBatteryManager
     - ApplePS2Controller
     - IOAHCISerialATAPI_Injector
     - DisableTurboBoostBattery
     - IntelBacklight
     - USBInjectAll
     - AppleHDA_ALC256

  
## DSDT Patches:
*Coming Soon*
Required for:
- WiFi
- Backlight Control 
- Audio

## Other:
### Sleep (automatic, menu bar and lid seem to work fine):
Run:

`sudo pmset hibernatemode 0`

`sudo rm -f /var/vm/sleepimage`

`sudo pmset hibernatefile /dev/null`

### [Smooth Scrolling](http://www.marcmoini.com/SmartScroll.zip)
- Smart Scroll by Marc Moini.


### [Brightness and Volume](https://pqrs.org/osx/karabiner/):
- Karabiner by Takayama Fumihiko


1. Launch Karabiner/Preferences/Misc & Uninstall
2. Under Custom Settings, click 'Open private.xml'
3. Replace file with the one from this repo.
4. Go back to Change Key Tab and select  'Reload XML'
5. The new custom file will show on the very top call 'Remap Brightness Key' & 'Remap Volumes Key'
6. Check the boxes beside F11 & F12 for Brightness, and F1, F2, & F3 for Volume Control





## Credits:
  * RehabMan (at TonyMacx86) - for helping me with the initial stuff
  * Jake Lo (at OS X Latitude) - for helping me with DSDT stuff, Audio, WiFi, Sleep, Backlight Control, Scrolling, and guide information.
  * Hervé (at OS X Latitude) - for research
  
