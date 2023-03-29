# hackintosh-coffeelake
 EFI folder for CoffeeLake i7-8700K machines
 
 ![2023-03-27_21-54-04](https://user-images.githubusercontent.com/60392496/228409475-e186f9b7-a6fc-4d56-9238-fff98478b5a4.png)

## Installation guide: 
  https://www.youtube.com/watch?v=4ryY9GTawQM&ab_channel=BarTechTV![image](https://user-images.githubusercontent.com/60392496/227962404-b8bdfc4c-15d3-45cc-b1b1-bbe21d823b61.png)

## Post-installation:
   1. Remove verbose boot:
      Remove -v in boot-args (under NVRAM):
      ![image](https://user-images.githubusercontent.com/60392496/227962586-7b7329e9-f3d2-4a97-bae0-04e302548f56.png)
   2. Remove opencore bootloader for fast boot into apple logo (under MISC): 
      Set showpicker=false 
      Should you have issues and need bootloader or boot in verbose refer to troubleshooting section under "Unable to boot due to bad kext".
      
## Working: 
   - Sleep
   - iservices
   - Ethernet
   - Audio
   - All usb slots works

## Not working (but can be solved with wifi card fenvi t919:
  - Bluetooth
  - Wifi
  - Airdrop
  - Handoff
  - Sidecar
  - Drag and drop - i had some issues with my machine dragging and not dropping. After serveral reboots it resolved itself.
  
  * currently testing: BCM943224 - from old A1466 macbook air with pciebt2 adapter https://shopee.sg/-risingmp-BCM94360CS2-BCM943224PCIEBT2-12-6-Pin-WIFI-wireless-card-module-to-NGFF-M.2-i.289662226.17292887793)

## Troubleshooting:
  - Unable to boot due to bad kexts: plug in your bootable usb > set boot drive to usb in bios > choose the drive that has mac installed > you should be able to boot into desktop now.
  - From my research seems like the bluetooth on Fenvi T919 operates on 2.4ghz band. Hence, some users has issues with spotty bluetooth and or slow wifi speeds when using 2.4ghz wifi + bluetooth simultaneously. The proposed solution is to use 5ghz band wifi and bluetooth issues should be fixed. Pending testing on this hypothesis.
