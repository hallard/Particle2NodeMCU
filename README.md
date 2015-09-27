Particle Spark/Photon to NodeMCU Adapter
========================================

This adapter is used to put in place of a Spark/Photon a NodeMCU board with ESP8266 I needed for a specific French [project][3]. I needed SPI for RFM69 Module with IRQ on ~~GPIO2~~ GPIO15 and SS on GPIO2 (see below why).
I choosed NodeMCU boards instead of ESP8266 because NodeMCU has all I needed on board, such as pullups, switches, USB power, 3/3V regulator, USB2Serial...

Since ESP8266 has less pin than Particle boards, only "classic" have been connected

- SPI Interface (GPIO12 to 14) GPIO15 is used for RFM69 IRQ
- I2C Interface (GPIO14 and GPIO5)
- Serial (GPIO1 and GPIO3)
- GPIO0 as free I/O (Flash button on NodeMCU)
- GPIO2 is used as Chip Select (SS) for RFM69
- GPIO16 as free I/O (LED and KEY on NodeMCU)

I discovered a major issue with 1st design, in fact ESP8266 to boot correctly needs some pins at defined level, GPIO15 must be LOW and GPIO2 must be HIGH.
Unfortunatlly with RFM69 connected as IRQ to GPIO2 and SS to GPIO15 it does not boot because RF69 pull it DIO IRQ to LOW, making GPIO2 LOW and ESP8266 not booting.
The fix is to reverse the wiring, connect IRQ to GPIO15 and SS to GPIO2 (and do according changes in the code). 
This page has been updated to reflect the changes and the PCB also, it's now V1.0a.

*Boards are still in progress, I did not tested them yet, I will update as soon has I got them in my hands. Use at your own risks*

Detailed Description
====================

Look at the schematics for more informations.

### Schematic  
![schematic](https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-sch.png)  

### Boards  
<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-top.png" alt="Top" width="40%" height="40%">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-bottom.png" alt="Bottom" width="40%" height="40%">&nbsp; 

If you have old version V1.0 PCB and a RFM69 attached, here the fix, cut line in red and solder wire on green line.   

<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-top-fix-gpio.png" alt="Top" width="30%" height="30%">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-bottom-fix-gpio.png" alt="Bottom" width="30%" height="30%">&nbsp; 


~~You can order the PCB of this board at [OSHPARK][4]~~ Old version, take care !!

### Assembled boards

I'm currently waiting for boards from OSHPARK
Boards arrived, I found one major issue with current wiring

##License

You can do whatever you like with this design.

##Misc
See news and other projects on my [blog][2] 
 
[2]: https://hallard.me
[3]: https://github.com/thibdct/programmateur-fil-pilote-wifi/tree/master/Logiciel/remora
[4]: https://oshpark.com/shared_projects/ot8OvWdM