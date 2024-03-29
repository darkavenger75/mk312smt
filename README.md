# mk-312 smt

## Introduction

A SMT version of the mk312-bt with several improvements

- More modern and efficient components in the power and output stage
- Input buttons more interference-proof to avoid the ATmega crashing
- And the best thing: someone like JLCPCB can do the assembly for you, you only need to add a few through-hole components and fit everything into the case. 

Main and control PCB are compatible with the THT versions, so that you can replace just one of them and keep the other PCB.

## Board ordering instructions 

PCB
- Default settings by JLCPCB work fine. Feel free to choose different color, etc. Lead-free recommended for the sake of the environment.

Assembly
- Economic, Bottom side (control PCB) / Top side (main PCB), as many PCBs as you wish. "Confirm Parts Placement" recommended. 
- Automatic selection of parts after uploading BOM and CPL worked well, but better check for obvious errors here and in part placement. 
- BOMs contain all components on the respective side, including the THT ones. If you want to place the THT parts yourself just deselect them.
- The LTC1661CMS or IMS is often not in stock. You might like to pre-order it to avoid buying it elsewhere and solding this tiny part.  

## Parts ordering information

You will in addition require
- All THT parts on the other side of the control PCB (buttons + caps, pots + knobs, display, brightness pot, 5mm LEDs), see the original BOM for information.
- Any part your manufacturer did not have in stock. In case of JLCPCB this means especially the 6 phone jacks, power socket, power switch, 42TU200 or 42TL004 transformers.
- A lead-acid battery of your choice. You can alternatively use a 12V LiFePO4 battery (with BMS), for that you need a matching charger (instead of the 15V power supply) and have to move the "jumper" (0R resistor) from "LDO" to "DIR" position to skip the voltage regulator. 

## Board assembly Instructions

Nothing special here, just add the THT parts missing and mount the control panel to the front panel.

## Firmware

The firmware has not been modified, for instructions see the "firmware" folder. 

## Case

Fits in the stadard PACTEC case, see original BOM. 

## Error 20

Some units may - more or less regularily - fail to start with "Error 20". The underlying reason is the firmware that is not tolerant againt sample variations in MOSFETs Q3, Q6.
The "original" MK312BT has the same issues. The only reliable way to fix this is to adjust the values of resistors R32, R43 (100k). I recommend trying somewhat lower/higher values (e.g. 82k and 120k) and check if your units boots realiably then.  
