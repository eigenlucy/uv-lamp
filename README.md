# uv-lamp
Open source flashlight kit

Made with atopile/KiCad

Ordering UVA-UVC flashlights on Amazon is notoriously a crapshoot. This project is designed to enable easy use of quality diodes instead :)

You can order a kit or an assembled unit from my tindie store (soonTM), or find everything you need to print and enclosure and order PCB/PCBA services below

Gerbers, BOM, and CPL files for PCBA JLCPCB PCBA services are automatically generated on each push in the build artifacts under the Actions tab

# BMS+LED Driver board:
ato.yaml :: ccdriver

entry: elec/src/ccdriver.ato

Based on the [TI BQ24040](https://www.ti.com/lit/ds/symlink/bq24045.pdf) battery charger IC (LCSC ID: C2870255) and [TI TPS61169](https://www.ti.com/lit/ds/symlink/tps61169.pdf?ts=1737056749253) LED Driver (LSCS ID: C71045)

# LED PCB
ato.yaml :: default

entry: elec/src/uv-lamp.ato

This should be manufactured as a 1.6mm thick 1W aluminum PCB rated. You should use a hot plate to assemble this for sure.

V1 designed for 1-3 3535SMD LEDs on 1.6mm aluminum core PCBs, but see instructions below to easily adapt for use with any diode you like (power/space permitting).

# Mechanical
Heatsink:
[SV-LED-214E](https://www.digikey.com/en/products/detail/ohmite/SV-LED-214E/4301037), 3D model + datasheet in mech/SV-LED-214E

Assembly BOM:
3 2-56 UNC x 5mm screws

# Atopile usage
[Atopile Docs](https://docs.atopile.io/latest/)

Atopile makes it easy to adapt this design for use with other diodes, drivers, BMS circuits, etc.

To change the LED package:

1: Fork this repo

2: Install [atopile from pypi](https://pypi.org/project/atopile/0.2.5/) with uv (recommended), pipx, or virtual fish. There is also a VCS extension for those inclined. Follow the instructions in the ato docs on setting up the kicad plugin,usually just ```$ ato configure```

3: find diodes you want/diodes using the package you want on the JLCPCB parts library, LCSC, or with [this tool](https://yaqwsx.github.io/jlcparts/#/) and install them into your project directory with 
```$ ato install --jlcpcb <LCSC_ID>```
For example, to install [WS2812B Neopixels](https://jlcpcb.com/partdetail/Worldsemi-WS2812B2020/C965555) with LCSC ID C965555:
```$ ato install --jlcpcb C965555```

4: open uv-lamp.ato in a text editor. import the module/component you've installed, eg:
```from "WS2812B_minus_2020.ato" import WS2812B_minus_2020```
check the pin names in the component ato file, and configure and interfaces you need. For other UV diodes, just ensure the pins are labeled A (anode) and K (cathode) and replace the components assigned to led1-led3:
```led1 = new M3535N1UVS8U06_minus_365NM -> led1 = new <COMPONENT>```
