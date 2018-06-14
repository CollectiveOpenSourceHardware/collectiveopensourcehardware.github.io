---
title: "Overview Libre Solar"
excerpt: ""
permalink: /education/libre_solar_overview/
---

In this chapter we first of all want to explain in general what Libre Solar is about, which components it contains and which applications it can be used for.

Libre Solar is an open hardware project for the development of a local energy network based on regenerative energy sources. Libre Solar contains the necessary electrical circuit boards (PCB - printed circuit boards), which are interconnected between energy producers (e.g. solar panels), energy storage devices (e.g. lithium ion batteries) and the load (electrical devices that we want to supply with electricity, e.g. our computer or freezer). Thus, a modular overall system can be set up, depending on the power and storage capacity requirements.


## Brief description of the components
The following electrical components are part of the Libre Solar project
- **MPPT** (**M**aximum **P**ower **P**oint **T**racker)
- **BMS** (**B**attery **M**anagement **S**ystem)
- **CAN2Wifi** (communication gateway)

### Maximum Power Point Tracker
![roadmap](/media_files/pcb_MPPT_charger_20A_rendered.png)
<br>

The MPPT module is a solar charge controller. This feeds the electrical power from the solar panels (Note: not only solar panels can be used as a source, but also small wind turbines or bicycle generators) in the connected battery storage. A direct connection of solar panels to a battery would destroy the battery after a short time, since there is no monitoring of the voltages and currents and thus the operating regulations of the battery are not carry out. Therefore, a charge controller is absolutely necessary.

The special feature of a MPPT charge controller is the optimal power consumption of a solar module. This is realized by tracking the voltage / current characteristic.
A detailed description of the MPPT function can be found in the following Wikipedia article - [Maximum Power Point Tracking](https://en.wikipedia.org/wiki/Maximum_Power_Point_Tracking).
The advantage of this method is the much higher efficiency of 95% to 99%. For comparison a simple charge controller without MPPT function, has an efficiency of about 70%.


The basic tasks of the Libre Solar MPPT Charge Controller are:
- Preventing overloading by overvoltage
- Preventing overcurrent by limiting the charging current
- PV short circuit
- PV reverse polarity
- Battery reverse polarity (fuse is blown)
- Stabilization of the output voltage at a voltage level

The built-in microcontroller allows the connection of different energy sources and energy storage devices by simple software adaptations.

### Battery Management System
The BMS module is optional as soon as lithium ion batteries are used.
Lithium ion batteries have a high energy density, so the energy capacity per kg. Thus, they are particularly well suited for mobile applications, such as in electromobility or in the consumer sector. The batteries in our mobile phones are also lithium ion batteries.
A disadvantage of this battery type is the sensitivity to overvoltage and deep discharge. Therefore, they require an upstream electrical circuit that covers these monitoring functions, a so-called Battery Management System (BMS).

In addition to the safety functions, the BMS module balances the connected batteries. This is necessary as soon as more than one battery cell is connected in series. Charging and discharging processes allow the capacitance between the individual battery cells to drift away from one another. This effect leads in the long term to a shorter life of the batteries and to a lower energy consumption. By balancing this effect is counteracted by the equalizing currents through balancing cells between the capacity.
A detailed description of the balancing process can be found at the following Wkipedia article - [Balancer](https://en.wikipedia.org/wiki/Balancer).

### CAN2Wifi
The CAN2Wifi module provides a communication gateway in which the data from the other two modules (MPPT and BMS) are processed via [CAN Bus](https://en.wikipedia.org/wiki/CAN_bus) and converted to W-Lan, so a web interface can be visualized.
This offers many possibilities in the area of Internet of Things (IoT). An example of the visualization of energy data is the Open Hardware Project [Open Energy Monitor](https://openenergymonitor.org/).

An example visualization of the energy values can be seen in the following picture.

![OEM](/media_files/introduction_openenergymonitor.png)

[Source: https://guide.openenergymonitor.org/images/applications/home-energy/myelectric_webapp.png, License: ]
