---
title: "Stencil Production"
permalink: /solarbox/stencil/
---

Before fitting all the small electronic parts on to the PCB we need to apply solder first. In this tutorial you learn how to create a reusable stencil which is used later to spread solder on to the whole board.

|  |  |
| --- | --- | --- |
| Material | Coated paper (eg. glossy magazine, Mylar or other materials) |
| Tools | Laser cutter, KiCAD |
| Needed skills | ... |
| Time | ... |
| Result | ... | 

---

Instead of applying solder manually to every solder joint we use a laser cutter to create a stencil which can be reused if you want to prepare more than one PCB. You will fix the stencil on the board so than you can all the solder junction but nothing else - afterward you spread solder on the board with a technique called *raking* which is explaned in the next tutorial. 

![fitting the stencil onto the PCB](/media_files/stencil_fit.jpg)

### KiCAD SVG export

The stencil can be created by exporting an image in SVG file format from the KiCAD board file. The process is similar to exporting a gerber file explained [in the PCB production tutorial](pcb_production.md). 

`Hier noch Klick-Video und/oder Beschreibung für SVG export!`

### Preparing the laser cutter

A laser cutter uses a focused high power laser to cut materials or engrave surfaces. Similar to a 3D printer or a CNC machine the laser beam is moved along two axes by a motion controller. There are software tools that generate motion commands from different file formats, in our case we use the open source software [VisiCut](http://hci.rwth-aachen.de/visicut-download) to use the laser cutter *Epilog Zing*.

![Epilog Zing laser cutter](/media_files/epilog_zing.jpg)![Epilog Zing laser cutter with materials](media_files/laser_cutter_with_materials.jpg)

The two most important parameters to determine if only the surface of a material is engraved or if the material is cut through are:
- the power of the laser beam
- the speed of the beam

The higher the power of the beam and the longer the beam stays at one place the deeper the beam cuts into the material. If the parameters are not correct, the beam won't cut through the material or even burn the material. Also note that different materials need different parameters to achieve the desired cut or engrave.