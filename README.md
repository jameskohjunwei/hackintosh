# hackintosh-coffeelake
 EFI folder for CoffeeLake i7-8700K machines

## Installation guide: 
  https://www.youtube.com/watch?v=4ryY9GTawQM&ab_channel=BarTechTV![image](https://user-images.githubusercontent.com/60392496/227962404-b8bdfc4c-15d3-45cc-b1b1-bbe21d823b61.png)

## Post-installation:
   1. Remove verbose boot:
      Remove -v in boot-args: -v alcid=11 igfxonln=1 watchdog=0 agdpmod=pikera dk.e1000=0 e1000=0
      [image](https://user-images.githubusercontent.com/60392496/227962630-68ec4706-1e5f-4983-8c22-fc56ababb9fc.png)

      ![image](https://user-images.githubusercontent.com/60392496/227962586-7b7329e9-f3d2-4a97-bae0-04e302548f56.png)

## Working: 
   - Sleep
   - iservices
   - Ethernet
   - Audio
   - All usb slots works

## Not working (but can be solved with wifi card fenvi t919):
  - Bluetooth
  - Wifi
  - Airdrop
  - Drag and drop - i had some issues with my machine dragging and not dropping. After serveral reboots it resolved itself.
