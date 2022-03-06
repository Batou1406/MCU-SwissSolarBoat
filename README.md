# MCU-SwissSolarBoat
written by : Baptiste Savioz, the 03.03.2022  
reviewed by : ..., the .. .. ....  
updaten by : ..., the .. .. ...  

# Introduction
This repository contains all required files and information for complete characterization of the main MCU-board of Swiss Solar Boat. Please read the documentation carefully before starting, especially the _Important things before starting_ section.

The main MCU-board is made of a powerfull microcontroller used for communication (based on the CAN protocol) between the differents modules of the boat. It also includes I2C lines with dedicated connectors for communication insides boat modules (eg. the battery box) and a SD card holder to save a logfile for example.

# ! Important things before starting !

# Documentation

## Sub-system characterization
### MCU
The board is based on ATSAME51J20A-AF MCU from atmel, using the 32-bit ARM® Cortex®-M4 processor with Floating Point Unit (FPU). It is running at 120 [MHz] on 3.3[V].

### Power supply
The board is powered with a 24[V] DC line that goes all along the boat. It can be quite noisy and therefore we choosed to graduatly decreased the voltage from 24[V] to 5[V]  through a high efficiency buck converter and then from 5[V] to 3.3[V] with a LDO IC. The LDO will power only the main board to ensure stable and clean power to it. On the other hand, the 5[V] power supply can be used by the shield to power other small devices. 

 * **Buck converter** : 24[V] DC to 5[V] DC  
The buck used is the TPS54233QDRQ1 from texas instrument. It has been designed with WEBENCH software from TI to operate at 20-28[V] in, 5[V] out, 2[A] out max, 50[°C].  
https://webench.ti.com/power-designer/switching-regulator?powerSupply=0

![image](image/buck_design_webench.svg)

 * **LDO** : 5[V] DC to 3.3[V] DC    
 The LDO used is the AP7365-33WG-7, which is a fixed output voltage LDO in the package SOT25. It not recommanded for new design and will shortly full out of supply. The newer version AP7366 is available but haven't been choosen because parts weren't available for now. However, switching to AP7366 wouldn't required adaptation of the PCB since it is also in the SOT25 package. Further update of this PCB may want to upgrade the LDO to an up to date version.

### Clock
- frequency of the MCU
- quartz horloger : 32768[Hz]
- quartz high freq

### Communication
- CAN
- I2C
- JTAG
- USB

### Connectors
- complete list of connectors

### SD-card and memory


## exhaustive list of component
|Component|name|number|reference|general purpose|usual reseller|link|
|---------|----|------|---------|---------------|--------------|----|
|Microcontroler|ATSAME51J20A-AF|1|CMP-002-000002-1|MCU of the board|Mouser|https://www.mouser.ch/ProductDetail/Microchip-Technology-Atmel/ATSAME51J20A-AF?qs=sGAEpiMZZMv0NwlthflBi1rrhCr8J09xsoDuGmx4aqk%3D|
|Buck|---|1|---|Power supply : convert 24V DC to stable 5V DC|---|
|LDO|---|1|---|Power supply : convert 5V DC to stable 3.3V DC|---|
|Crystal|---|1|---|Frequency generation for the MCU|---|


## Pinout and Shield
pinout schematic and shield characterization


## physical adress of modules
|Module|protocol|Address|general purpose|
|------|--------|-------|---------------|
|dummy|I2C|0xfh6c|dummy module used for example|

 Repository for documentation, characteristics and all required elements for the Microcontroller board, including PCB conception, of SSB.
