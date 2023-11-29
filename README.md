# hackintosh-coffeelake
 EFI folder for CoffeeLake i7-8700K machines
 
 ![2023-03-27_21-54-04](https://user-images.githubusercontent.com/60392496/228409475-e186f9b7-a6fc-4d56-9238-fff98478b5a4.png)

## Installation guide: 
  https://www.youtube.com/watch?v=4ryY9GTawQM&ab_channel=BarTechTV![image](https://user-images.githubusercontent.com/60392496/227962404-b8bdfc4c-15d3-45cc-b1b1-bbe21d823b61.png)

## Bios: 
   1. vt-d | disabled
   2. CSM | enabled, UEFI only and in "other OS" mode
   3. Secure boot | disabled, erase keys if required to disable
   4. [Critical] remove dedicated graphics card if you see "unsupported PCH" error in logs

## Post-installation:
   1. Remove verbose boot:
      Remove -v in boot-args (under NVRAM):
      ![image](https://user-images.githubusercontent.com/60392496/227962586-7b7329e9-f3d2-4a97-bae0-04e302548f56.png)
   2. Remove opencore bootloader for fast boot into apple logo (under MISC): 
      Set showpicker=false 
      Should you have issues and need bootloader or boot in verbose refer to troubleshooting section under "Unable to boot due to bad kext".
   3. Boot without install drive. Install OC configurator on your hackintosh. On the top right toolbar, mount the disk that you installed macos.
      ![image](https://github.com/jameskohjunwei/hackintosh/assets/60392496/e15edfa2-46ed-4154-bc9b-149ba5b5b875)

      Once mounted, you will see a EFI folder, delete everything in it, drag the full EFI folder from your thumb drive into this EFI directory
      ![image](https://github.com/jameskohjunwei/hackintosh/assets/60392496/9ee58f9e-e537-4477-8f27-3874c8d6283d)
      
## Working: 
   - Sleep
   - Bluetooth
   - Wifi
   - iservices
   - Ethernet
   - Audio
   - All usb slots works

## Not working (but can be solved with wifi card):
  - Airdrop
  - Handoff
  - Sidecar
  - Drag and drop - I had some issues with my machine dragging and not dropping - solved by changing the logi adapter to motherboard's usb 3.0 slot.
  
  * (test completed): fenvi t919 card doesn't work well for me. Bluetooth doesn't work at all despite the right kext, and wifi is really slow for 5ghz. 
  * (test completed): BCM943224 - from old A1466 macbook air with pciebt2 adapter. This works well for me, but airdrop doesn't work. https://shopee.sg/-risingmp-BCM94360CS2-BCM943224PCIEBT2-12-6-Pin-WIFI-wireless-card-module-to-NGFF-M.2-i.289662226.17292887793)

## Troubleshooting:
  - Unable to boot due to bad kexts: plug in your bootable usb > set boot drive to usb in bios > choose the drive that has mac installed > you should be able to boot into desktop now.
  - From my research seems like the bluetooth on Fenvi T919 operates on 2.4ghz band. Hence, some users has issues with spotty bluetooth and or slow wifi speeds when using 2.4ghz wifi + bluetooth simultaneously. The proposed solution is to use 5ghz band wifi and bluetooth issues should be fixed. Test completed, Fenvi doesn't work for me.
  
## Homebrew + vscode issues:
  - Whenever you restore your mac from time machine there might be issues to your coding env. Refer to this and install xcode again https://apple.stackexchange.com/questions/254380/why-am-i-getting-an-invalid-active-developer-path-when-attempting-to-use-git-a
  - uninstall homebrew /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"copied to clipboardcopied to clipboardcopied to clipboardcopied to clipboard
  - make sure you look at opt and local folders to see all brew is uninstalled. 
  - brew help in terminal to see if brew exists.
  - Install brew again, in intel macs it /HomeBrew will appear in /local folder.

## Tools:
  - OC Configurator (to mount boot drive, update and validate kexts, and find out what kexts work for your hardware)
