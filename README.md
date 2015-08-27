Particle Spark/Photon to NodeMCU Adapter
========================================

This adapter is used to put in place of a Spark/Photon a NodeMCU board with ESP8266 I needed for a specific French [project][3]. I needed SPI for RFM69 Module with IRQ on GPIO2.
I choosed NodeMCU boards instead of ESP8266 because NodeMCU has all I needed on board, such as pullups, switches, USB power, 3/3V regulator, USB2Serial...

Since ESP8266 has less pin than Particle boards, only "classic" have been connected

- SPI Interface (GPIO12 to 15)
- I2C Interface (GPIO14 and GPIO5)
- Serial (GPIO1 and GPIO3)
- GPIO0 as free I/O (Flash button on NodeMCU)
- GPIO2 as free I/O 
- GPIO16 as free I/O (LED and KEY on NodeMCU)

*Boards are in progress, I did not tested them yet, I will update as soon has I got them in my hands. Use at your own risks*

Detailed Description
====================

Look at the schematics for more informations.

### Schematic  
![schematic](https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-sch.png)  

### Boards  
<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-top.png" alt="Top" width="40%" height="40%">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/Particle2NodeMCU/master/Particle2NodeMCU-bottom.png" alt="Bottom" width="40%" height="40%">&nbsp; 

You can order the PCB of this board at [OSHPARK][4]

### Assembled boards

I'm currently waiting for boards from OSHPARK

##License

You can do whatever you like with this design.

##Misc
See news and other projects on my [blog][2] 
 
[2]: https://hallard.me
[3]: https://github.com/thibdct/programmateur-fil-pilote-wifi/tree/master/Logiciel/remora
[4]: https://oshpark.com/shared_projects/ot8OvWdM