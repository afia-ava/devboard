# Journal 1

usb-c powered rp2040 board with onboard qspi flash, crystal timing, debug header, and full gpio breakout for prototyping.

### components
**power**  
usb-c receptacle (j1) as sole power/data input, with 5.1k cc1/cc2 pull-downs for usb-c power negotiation  
ncp1117-3.3 ldo (u2) regulating vbus down to 3v3  
input/output stabilization caps (10uf) on the regulator  
full decoupling bank (1uf/0.1uf) across the 3v3 rail for the rp2040's vdd pins

**core**  
rp2040 (u1), internal switching regulator generating the 1v1 core rail  
12mhz crystal (y1) with 1.5pf load caps and drive resistor for the system clock  
w25q128jvs qspi flash (u3, 16mb) — external program storage, since rp2040 has none onboard

**debug & io**  
swd header (j4) for flashing/debugging  
user pushbutton (sw1) with pull-up into a gpio  
gpio pin headers (j2, j3) breaking out remaining pins for prototyping

**erc notes**  
a few recurring fixes during schematic cleanup:  
i edited parts of the symbols on symbol editr which kept ghost symbols which were hidden- quick fix is basically looking for all the light shaded pins and parts wandering around the drawing sheet. 
for duplicate pin numbers editing it on symbol editor to remove the ghost numbers worked 
the power pin error is good to ignore, or a pwr_flag can be added to reassure that we have external power source 

time spent: approx 5 hrs 
