# HybridOS

HybridOS is a totally new open source operating system designed for smart IoT devices
and cloud computing environment.

HybridOS tries to provide the developers with more possibilities than just a
traditional operating system for a stand-alone hardware environment.

HybridOS not only runs on smart IoT devices to support application development
on devices, but also provides programming interfaces for the cloud and the clients.
It tries to give the developers a new complete software stack and protocol stack 
from devices to the cloud and the clients.

## Table of Contents

[Why We Design a New OS for IoT?](#why-we-design-a-new-os-for-iot)  
[Technical Terminologies](#technical-terminologies)  
[Goals of HybridOS](#goals-of-hybridos)  
[Design Documents and Specifications](#design-documents-and-specifications)  
[Source Tree](#source-tree)  
[Current Status](#current-status)  
[Copying](#copying)  

## Why We Design a New OS for IoT?

At present, when we want to develop a consumer IoT (Internet of Things) device, 
we have to build a software team which has five engineers at least due to 
the complex software stack and protocol stack of IoT computing environment:

* At least one firmware engineer who writes programs in C/C++ for the IoT device, which
  generally runs a RTOS or Linux.
* At least one server engineer who writes programs in Java/PHP/Python for the cloud services.
* At least one front-end engineer who writes webpages in JavaScript/CSS/HTML5 for webpages.
* At least two client-end engineers who write apps in Java, Objective C, or Swift
  for smart phones, which run Android or iOS.

In addition, for some devices which are used for business, we need one or two engineers
to write desktop apps in C/C++ for Windows, macOS, or Linux.

Obviously, the development cost of an IoT device is much higher than a traditional 
embedded device. We need a new operating system to simplify the software and protocol
stack of IoT applications, and reduce the development cost.

Not only that, the popular cloud computing services we can get from AWS, Ali, or Huawei
are not dedicated for IoT applications. We have to develop some cloud services by ourselves
to implement some features for our IoT devices. Moreover, the security of an IoT service 
is being seriously challenged.

For example, with the development of IoT technologies, we can now use our own smart phone
to remotely control the home air conditioner or view the home camera in real time. 
We can even use the smart phone to remotely open our home door from the office.
However, have you ever thought about the issue: how your smart lock knows that the received
door open command is sent by you? Or, conversely, is the real-time monitoring screen that
you see on your smart phone generated by your own camera?

The reality is that any cracker who breaks into the cloud can easily control 
all IoT devices connected to the cloud remotely, including your smart door locks or
cameras. The current IoT products, like traditional Internet applications, have not 
improved much in terms of security. The scenes that we can often see from spy war 
movies can still be easily performed in reality.

The blockchain technology may change this. The decentralized design of the blockchain
provides another way to enhance the security of IoT. HybridOS will try to use the 
technologies to improve the security of IoT.

## Technical Terminologies

* Device: The IoT device; For HybridOS, the device here refers to a smart
  device that has direct access to the Internet and with or without a display.
* Device App: An app runs on a device, with or without GUI.
* Client: A desktop computer, a smart phone, or a tablet.
* Client App: An app runs on a client.
* Node: The IoT node; For HybridOS, the node here refers to a constrained IoT
  device in a constrained network.

## Goals of HybridOS

### A specialized software stack for IoT

HybridOS provides a new software stack for IoT applications:

* A new and universal app framework for IoT devices and client apps.
  The developers can write device app and client apps for Linux, Windows, macOS, 
  Android, and iOS operating systems by using a set of extended HTML5 tags 
  and JavaScript/CSS. You can even embed your HybridOS app directly
  in your webpages which are written in standard HTML5 by importing the HybridOS
  JavaScript and CSS library.

* A new implemantaion for common server, such as MQTT, WebSocket, HTTP,
  CoAP, and streaming servers. HybridOS provides a different 
  architecture for the implementation of the servers: any HybridOS app or
  service can register and work as a real service provider of the servers. 

Finally, the application programming languages of HybridOS will be reduced to two: 
JavaScript for apps and Python for services. As a result, the development cost of 
an IoT application will be reduced greatly by using HybridOS.

### IoT-dedicated cloud computing services

HybridOS integrates some cloud computing services which are dedicated to IoT,
such as a distributed MQTT server, identity authentication mechanism, 
and some basic services, such as firmware and app upgrade.

HybridOS will introduce the serverless technology for the IoT cloud
computing. In this way, the developer can easily integrate the existed
cloud services by writing a simple script in Python.

In the future, HybridOS will try to provide a blockchain-based IoT security
service. HybridOS will provide an enhanced MQTT implementation for
communication between things and an identity authentication mechanism
based on blockchain technology/idea.

### Rich connectivities

On the device side, HybridOS integrates a standard peripheral and task
management interface based on hBus (an enhanced edition of OpenWRT's uBus),
such as networking management, sensor (like GPS and gravity accelerometer)
management, and USB interface management. hBus exchanges data among apps
and services in JSON, which is friendly for any programming language.

HybridOS will provide a variety of connectivity options for the IoT devices, 
including 4G/LTE, NB-IoT, Wi-Fi, Bluetooth, ZigBee, NFC, RFID, USB, Ethernet,
RS232, and so on. 

The device-side system of HybridOS is based on the Linux kernel, making
full use of the Linux kernel ecosystem, reducing the difficulty of developing
various drivers and the difficulty of supporting various protocol stacks,
thus reducing development cost.

## Design Documents and Specifications

* [HybridOS Architecture]
* [HybridOS App Framework]
* [HybridOS Foundation Class Library]
* [HybridOS Security Design]
* [HybridOS Device Simulation Environment]
* [HybridOS Code Convention]

## Source Tree

    `
    |-- docs/           # The design documents for HybridOS.
    |-- device-side/    # The source for device side.
    |-- server-side/    # The source for server side.
    |-- client-side/    # The source for client side.

    
## Current Status

* Nov. 2018: Initiate this project organize specifications and design documents.

## Copying

Copyright (C) 2018 [Beijing FMSoft Technologies Co., Ltd.]

* For device side and client side, HybridOS uses GPL v3.
* For server side, HybridOS uses AGPL v3.
* For documents, GPL v3 applies.

Note that HybridOS integrates many mature open source software, such as SQLite, FreeType, 
V8 JavaScript engine, and so on. For the copyright owners and licenses for these software, 
please refer to the README or LICENSE files contained in the source trees.

[Beijing FMSoft Technologies Co., Ltd.]: http://www.fmsoft.cn
[FMSoft Technologies]: http://www.fmsoft.cn
[HybridOS Official Site]: http://www.hybridos.org

[HybridOS Architecture]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0000.md
[HybridOS App Framework]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0001.md
[HybridOS Foundation Class Library]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0002.md
[HybridOS Security Design]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0003.md
[HybridOS Device Simulation Environment]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0004.md
[HybridOS Code Convention]: https://github.com/VincentWei/hybridos/blob/master/docs/HYBRIDOS-SPEC-0005.md

