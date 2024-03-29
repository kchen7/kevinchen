---
title: "Penn Electric Racing"
layout: post
date: 2020-05-11 11:11
tag:
  - altium
  - stm32
headerImage: true
image: ../assets/images/per/logo.png
description: "This page documents my experiences with Penn Electric Racing"
projects: true
category: project
externalLink: false
---

## The Team
Penn Electric Racing is a student run engineering team that competes in the
Formula SAE Electric. We've historically built electric racecars that
rank top three internationally at competitions such as FSAE Lincoln and
have held the record for fastest acceleration time. More information about the team can be found on
<a href="https://www.pennelectricracing.com/" target="_blank" rel="noopener noreferrer"> our website!</a>

![REV 5 Unveiling](../assets/images/per/unveiling.jpg "REV 5 Unveiling")

---
## Responsibilities
<div class="side-by-side">
    <div class="toleft">
        <p> The hardware subteam designs, reviews, and tests
            about 15 custom four-layer PCBs each year. Our designs include
            a LCD dashboard, an e-fused power distribution unit, and
            a powertrain control module.
        </p>
        <p> As the electrical lead, I managed the timelines for and reviewed all of these
            boards. However, I worked most closely with designing the
            Battery Management System. More details are included below.
        </p>
    </div>
    <div class="toright">
        <img class="image" src="../assets/images/per/gerbers.png" alt="gerbers" width="300">
        <!-- <figcaption class="caption">Board Gerbers (2018)</figcaption> -->
    </div>
</div>

I've also fostered team growth by documenting our designs on Confluence,
developing a new member curriculum, and speaking recruiting events,
such as info sessions or club fairs.

![2019 Info Session](../assets/images/per/info-session.jpg "2019 Info Session")

---
## Battery Management System

The semi-distributed, battery management system monitors a 300V battery
made of 576 lithium ion cells. These cells are connected in a 72s8p
configuration and broken up into eight 9s8p substacks. Within each
substack, the cells are welded together on a flexible PCB containing fuses,
cell taps, and thermistors. A daughter board sits above the substack,
connecting to the flexible PCB to measure and balance the voltage of the
cells using the LTC6811 battery monitor. The daughter also measures cell
temperatures with the thermistors through a mux.  

![Single Substack](../assets/images/per/exploded-substack.png "Single Substack")

These eight daughter boards are daisy-chained together and communicate
with the motherboard through the LTC6820 isoSPI interface. This board
also monitors the battery at a macro-level, measuring voltage, power draw,
and insulation. It contains a STM32F7 microcontroller that analyzes the
data for faults, closing the battery isolation relays only when safe.
Finally, the motherboard pre-charges the motor controllers on startup and
communicates with the rest of the car using CAN. The CAD and PCB are displayed below. 

![BMS CAD](../assets/images/per/bms-cad.jpg)

![BMS](../assets/images/per/bms-pic.jpg)

---
## PCB Ruler

Inspired by other PCB rulers such as the ones made by Digi-Key or Nvidia,
I decided to design one for Penn Electric Racing to use as merchandise.
I opted for a 6" design, rather than 12", for improved portability.
In addition to being merchandise, I wanted the ruler to be a useful
resource to members on the hardware team, so it is covered with layout and electrical engineering references: 

![Front of Ruler](../assets/images/per/ruler-front.png)

The PCB was finished with black solder mask and lead-free HASL to
match Penn Electric Racing's colors. The final product is pictured below!

![Ruler](../assets/images/per/ruler-picture.jpg "End Result")

---

<div align="center">Finally getting to drive :)</div>
![REV 5](../assets/images/per/car.jpg "Me sitting in REV 5!")
