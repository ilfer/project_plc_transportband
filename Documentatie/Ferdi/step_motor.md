# Stepper motor

<img src="https://i.postimg.cc/XqqWKYyp/bckhff.png" width="150">

## About
Because the DC motor was not powerful enough to control the conveyor belt, we decided to use a stepper motor that is more powerful.

### Table of Contents
1. [Materials and methods](#MM)
2. [Hardware](#H)
3. [Software](#code)
   - 3.1 [Startup](#SU)
4. [Result](#R)
5. [Solution](#S)

---

## 1. Materials and methods <a name="MM"></a>

- Stepper motor: [Beckhoff AS1010-0000](https://www.beckhoff.com/nl-be/products/motion/compact-drive-technology/asxxxx-stepper-motors/as1010.html) stepper motor 0.38 Nm (M0), N1 (NEMA17/42 mm)
- PLC card for the stepper motor: EL7332
- Motor cable (type unknown)

## 2. Hardware <a name="H"></a>

The connection between the PLC and the stepper motor is made using a motor cable. The first image shows the connection.

On the second image the motor cable is visible. The 4 wires are separated per 2 (phases). The red wire is connected to the connection A1 (see figure on the right) on the EL7031 (PLC card). The blue card is then connected to the A2. Furthermore, the grounding cable is connected to the B1 and the white cable to B2.

The other side of the motor cable is connected with the cable that is attached to the motor. This connection is simply made by turning in the cable.

<p float="left">
  <img src="https://i.postimg.cc/HsVCJFTk/IMG-9162.jpg" width="200" />
  <img src="https://infosys.beckhoff.com/content/1033/ep7342-0002/Images/png/3662419467__Web.png" width="350" /> 
  <img src="https://infosys.beckhoff.com/content/1033/el70x1/Images/gif/2257942795__en-US__Web.gif" width="350" />
</p>


## 3. Software <a name="code"></a>
After creating a twincat project, we first set certain parameters that have to do with the specifications of the motor.

  ### 3.1 Startup <a name="SU"></a>
  Starting with the Startup we provide the right basic specifications of the stepper motor. This largely contains the power supply or the load that the engine can handle.

   We set parameters here such as maximum current, voltage and resistance motor coil. All these parameters can be found in [beckhoff's data sheet](https://download.beckhoff.com/download/Document/motion/as1000_ba_en.pdf).
   
  <img src="https://i.postimg.cc/RhzzJLLV/s.png" width="500">

## 4. Result <a name="R"></a>


## 5. Solution <a name="S"></a>


<br />

*time spent: April 22 to June 3 (6 weeks -> 4 hours * 6 = 24 hours)*
