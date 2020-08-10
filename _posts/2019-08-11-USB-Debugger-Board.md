---
title: "USB Debugger Board"
layout: post
date: 2019-08-11 11:11
tag:
  - altium
  - stm32
headerImage: false
#image:
description: "A board designed to debug products for an internship"
projects: true
category: project
externalLink: false
---

## Background

I designed this board for an internship program. Broadly, this board
(playfully nicknamed "Blueberry") had two goals. First, the old testing
station on the manufacturing line was messy as it contained multiple
boards. Blueberry aimed to simplfy the station by consolidating all the
functionality onto one board. Second, Blueberry was to be a single tool
that the firmware team could use to debug the PCBs in each product.

## Requirements
![Annotated Screenshot](../assets/images/blueberry/annotated.png)

The main input to the board is USB, which connects to the TUSB2046I, a
4-Port USB hub. One hub output is translated to 4 UART streams on a
header and another to isolated RS485. These are the main outputs used to
communicate with products. A third hub output interfaces with the
STM32F1 microcontroller and the last is just outputted for the user.

The second input is a barrel jack for power. The TPS2121 power mux
ensures that although the barrel jack isn't necessary for operations
mentioned in the previous paragraph, power will be drawn from it
instead of the USB input when possible. The primary use for this input,
though, is to power the device under test. Blueberry has two power
outputs: 12V and a programmable voltage. The power consumption for these
outputs is monitored with the INA226.

![Blueberry](../assets/images/blueberry/blueberry.jpg)
