# uv-lamp
Open source flashlight kit

Made with atopile/KiCad

Ordering UVA-UVC flashlights on Amazon is notoriously a crapshoot. This project is designed to enable easy use of quality diodes instead :)

You can order a kit or an assembled unit from my tindie store (soonTM), or find everything you need to print and enclosure and order PCB/PCBA services below

Gerbers, BOM, and CPL files for PCBA JLCPCB PCBA services are automatically generated on each push in the build artifacts under the Actions tab

V1 designed for 1-3 3535SMD LEDs on 1.6mm aluminum core PCBs, but see instructions below to easily adapt for use with any diode you like (power/space permitting).

# BMS+LED Driver board:
ato.yaml :: ccdriver

entry: elec/src/ccdriver.ato

Based on the [TI BQ24040](https://www.ti.com/lit/ds/symlink/bq24045.pdf) battery charger IC (LCSC ID: C2870255) and [TI TPS61169](https://www.ti.com/lit/ds/symlink/tps61169.pdf?ts=1737056749253) LED Driver (LSCS ID: C71045)

# LED PCB
ato.yaml :: default

entry: elec/src/uv-lamp.ato

Hold 1-3 3535 SMD LEDs by default

To be manufactured as a 1.6mm thick 1W aluminum PCB rated. You should use a hot plate to assemble this for sure.

# Mechanical
Heatsink:
[SV-LED-214E](https://www.digikey.com/en/products/detail/ohmite/SV-LED-214E/4301037)

3D model + PDF in mech/SV-LED-214E
