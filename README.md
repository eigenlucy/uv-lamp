# uv-lamp
Open source flashlight kit
Made with atopile, KiCad, and FreeCAD
Ordering UVA-UVC flashlights on Amazon is notoriously a crapshoot. This project is designed to enable easy use of quality diodes instead :)
You can order a kit or an assembled unit from my tindie store (soonTM), or find everything you need to print and enclosure and order PCB/PCBA services below

Gerbers, BOM, and CPL files for PCBA JLCPCB PCBA services are automatically generated on each push in the build artifacts under the Actions tab
V1 designed for 1-3 3535SMD LEDs on 1.6mm aluminum core PCBs, but see instructions below to easily adapt for use with any diode you like (power/space permitting).

# BMS+LED Driver board:
ato.yaml :: ccdriver
entry: elec/src/ccdriver.ato

# LED PCB
ato.yaml :: default
entry: elec/src/uv-lamp.ato

# Mechanical
Designed in FreeCAD
Heatsink:
[SV-LED-214E](https://www.digikey.com/en/products/detail/ohmite/SV-LED-214E/4301037)
3D model + PDF in mech/SV-LED-214E
