---
title: "Libre Solar Box"
permalink: /hardware/solarbox_intro/
---
This Open Hardware project is about the development of a solar box.
We want to provide a compact, mobile and modular electric power generator. An alternative to the diesel generator.
The power specifications are chosen to supply a mini house, a boat, a caravan, or any other off-grid devices like a music station on an open-air.

The aim is that everybody is possible to rebuild the solar box at home or at his/her favourite fablab.

----------------------

## Documentation still under development...

You find our development process of the solar box on following [GitHub repository](https://github.com/CollectiveOpenSourceHardware/LibreSolarBox). Feel free to fork and contribute.

## Some impressions...

<!--![Libre Solar Box Layout](/media_files/libre_solar_box_layout.png)-->

<iframe src="https://h5p.org/h5p/embed/231072" width="1091" height="690" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Overview of the Libre Solar Box layout.

![solarbox_freeCAD](/media_files/solarbox_v02_freecad.jpg)

CAD model of the solarbox V0.2 designed in [FreeCAD](https://www.freecadweb.org/).

![solarbox_freeCAD](/media_files/solarbox_v02_real.jpg)

Finshed assembly of the solarbox V0.2 with wood housing and acrylic glas on one site.



## Specifications:
- Maximal Voltage Input = **55 V**
- Maximal Power Input = **300 Wp**
- Capacity of Batteries = **920 Wh**
- DC Output Voltage = **12 V** and **5 V** (USB-power)
- Maximal Power Output = **600 W**

### modules:
- **electric**: [Libre Solar](http://libre.solar/) (MPPT+BMS), Inverter (Victron), ESP/Rasbperry, Fuse
- **Batteries**: LiFePO4 (Calb), 72Ah, 3,2V, 230,5Wh - 4x -> 12,8V, 920Wh
- **Housing/Frame**: [UniProKit](https://wiki.opensourceecology.de/Upklib), with corner elements for blending; wood plates for mounting electric parts and batteries
- **Interface**: Solarinput (MC4), DC-output (car plug), AC-output (schuko, integrated in inverter), main switch

### visualization:
- [Open Energy Monitor](https://openenergymonitor.org/) via CAN to ESP (Server ext.)/Rasbperry (Server int.)
- browser based visualization -> access via LAN/WLAN

