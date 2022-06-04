# Stepper motor

<img src="https://multimedia.beckhoff.com/media/as1010-0000__web_preview.png" width="250">

## About
Because the DC motor was not powerful enough to control the conveyor belt, we decided to use a stepper motor that is more powerful.

## Materials and methods

- Stepper motor: [Beckhoff AS1010-0000](https://www.beckhoff.com/nl-be/products/motion/compact-drive-technology/asxxxx-stepper-motors/as1010.html) stepper motor 0.38 Nm (M0), N1 (NEMA17/42 mm)
- PLC card for the stepper motor: EL7332
- Motor cable (type unknown)

## Hardware

The connection between the PLC and the stepper motor is made using a motor cable. The first image shows the connection.

On the second image the motor cable is visible. The 4 wires are separated per 2 (phases). The red wire is connected to the connection A1 (see figure on the right) on the EL7031 (PLC card). The blue card is then connected to the A2. Furthermore, the grounding cable is connected to the B1 and the white cable to B2.

The other side of the motor cable is connected with the cable that is attached to the motor. This connection is simply made by turning in the cable.

<p float="left">
  <img src="https://i.postimg.cc/HsVCJFTk/IMG-9162.jpg" width="200" />
  <img src="https://infosys.beckhoff.com/content/1033/ep7342-0002/Images/png/3662419467__Web.png" width="350" /> 
  <img src="https://infosys.beckhoff.com/content/1033/el70x1/Images/gif/2257942795__en-US__Web.gif" width="350" />
</p>


## Software


## Result


## Solution


<br />

*time spent: April 22 to June 3 (6 weeks -> 4 hours * 6 = 24 hours)*
