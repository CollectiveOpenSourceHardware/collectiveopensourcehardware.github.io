---
title: "Step 5 - Wiring Electric"
excerpt: ""
permalink: /education/solarbox_assembly_guide/wiring_electric/
---

## Assembly interface bleding
The interface blending is the blending with sockets.
* Put sockets with cables into the blending
* Mount the interface bleding to the frame

## Connect BMS
* Solder cables to the on/off-switch.
* Mount blue thick cables and USB+ to *PWR-* of BMS.
* Mount red thick cables and USB- to *PWR+* of BMS.
* Connect two blue cables (- or +?) to two DC out sockets.
* Connect two red cables to two DC out sockets.
* Connect two thin cables from on/off-switch to BMS.

## Connect to MPPT
* Connect all cable ends without blade connectors to MPPT.
* Check that these cable are well mounted.

## Connect battery block
(In this part BAT- and BAT+ seems to be confused.I need resolve it.)
* Remove isolation from **main -**.
* Connect two cables to **main -**.
* Connect thick blue cable to *BAT-* on BMS.
* Connect two cables to **main -**
* Connect balancing to *BAT-* on BMS. (Is this correct?)
(Must the on/off switch must be off before add the fuse? How one can see it?)
* Add fuse.
* Check the voltage (where?): It must be around 12.8 V.
* Switch off the on/off switch.
* Check the voltages. It must be falling until 0. The voltage does not drop imidiatelly to 0, because there is remaining electric charge in the capacitors.
* Swich on.
* Check Voltage between *POW+* and *POW-*. It must be about 12.8V.
* Remove the fuse. (I missted this step in my notes. Is it correct here?).

## Connect Raspberry
Optional you can use a Raspberry for monitoring the solarbox data.

* Connect  an internet cable to Raspberry
* Connect the internet cable to BMS.
* Connect an internet cable to CAN socket on the blending.
* Connect the other end of the cable to BMS.
* Mount the Raspbery with two-side tape to the box.
