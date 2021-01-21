---
title: OSI-model
description: 
published: true
date: 2021-01-21T15:15:32.239Z
tags: 
editor: markdown
dateCreated: 2021-01-21T15:09:52.659Z
---

# OSI-model
[Open Systems Interconnection-model](https://en.wikipedia.org/wiki/OSI-model) 
![Different layers in OSI-model](http://electricala2z.com/wp-content/uploads/2017/10/osi-model.gif)

Extra explanation in book on page 276.

## Layer 7: Application Layer
This layer is where the application and user communicates
Applications used here such as SMPT, if youre sending an email for example.

Example:
- Is the application erroring out?
    
## Layer 6: Presentation layer
 This layer formats the data in a way the reciving application can understand it. This layer can also encrypt and decrypt data if needed

Example:
- Are you reading the data in the same order that you wrote it?

## Layer 5: Session layer
this layer is responsible for establishing and terminating connections between devices.

Example:
- Are you connecting to the correct address?

## Layer 4: Transport layer
This layer adds transport protocols such as TCP/UDP, and adds source/destination
port numbers.

Example:
- Could the internet card be functional?

## Layer 3: Network layer
The network layer handles ip addressing and routing. At this layer, the source
and destination IP addresses are added.
Routers operate at this layer

Example:
- Is the router functioning?
- Do i have the right IP address?

## Layer 2: Data Link layer
At this layer, the physical addresses are added to the data. This is source and
destination mac addresses.
Switches operate at this layer

Example:
- Maybe the switch has gone bad?

## Layer 1: Physical layer
carries data across physical hardware.
Uses: ethernet cables.

Examples:
- are all the cables plugged in?
- Is the network card functioning?
- Could it be a faulty cable?

## Accronym
Something to help you learn:
7: All - Application
6: People	- Presentation
5: Seem	- Session
4: To	- Transport
3: Need	- Network
2: Data	- Data
1: Processing	- Physical

Source: https://youtu.be/LANW3m7UgWs