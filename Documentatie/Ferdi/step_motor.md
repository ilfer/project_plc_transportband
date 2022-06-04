# Stepper motor

<img src="https://i.postimg.cc/XqqWKYyp/bckhff.png" width="150">

## About
Because the DC motor was not powerful enough to control the conveyor belt, we decided to use a stepper motor that is more powerful.

### Table of Contents
1. [Materials and methods](#MM)
2. [Hardware](#H)
3. [Software](#code)
   - 3.1 [Startup](#SU)
   - 3.2 [Other parameters ](#OP)
   - 3.3 [Program](#twincat)
   - 3.3.1 [MC_Power](#power)
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
   
*These parameters can also be imported via this [XML file](https://github.com/ilfer/project_plc_transportband/blob/5f5fdd1edf0ba534ac298b7523b0595765bade60/tb_step_motor/StartUp.xml).*
   
<img src="https://i.postimg.cc/RhzzJLLV/s.png" width="500">
  
### 3.2 Other parameters <a name="OP"></a>
Furthermore, other parameters need to be set. These parameters are important that are used later in a program. The value of the parameters must be determined in advance or looked up in data sheets. Axis 1 sets parameters that include speed, acceleration, and so on.

Other parameters must also be set in 'Enc' and 'Drive'.
   
*The parameters in the image are default values.*
<img src="https://i.postimg.cc/zGbZct7v/parameters.png" width="1000">
  
### 3.3 Program <a name="twincat"></a>
#### 3.3.1 MC_Power <a name="power"></a>
      
MC_Power takes care of switching on the engine. In every engine application, this function block is necessary. It only ensures that we can use the engine and therefore does not let the engine run.

The most important inputs that we have to give are the Axis (coupling with the stepper motor), enable (activating the MC_Power), enable positive/negative and override. The remaining entries include error codes.
      
<img src="https://infosys.beckhoff.com/content/1033/tcplclib_tc2_mc2/Images/png/9007199324926603__Web.png" width="300">

#### 3.3.2 MC_Jog <a name="jog"></a>

Another function block that we use is the MC_Jog. This ensures that we can control the engine more manually.
The motor can be controlled when we set the inputs 'JogForward' or 'JogBackwards' high. The motor only remains in operation as long as one of these inputs becomes high. We can also give the speed and distance.

<img src="https://infosys.beckhoff.com/content/1033/tcplclib_tc2_mc2/Images/png/9007199325083403__Web.png" width="300">

#### 3.3.3 MC_MoveRelative <a name="mrelative"></a>

MC_MoveRelative is similar to MC_Jog. The MC_MoveRelative makes it easier because here we can enter the distance that the engine must achieve.  The motor operates until the distance is reached.

<img src="https://infosys.beckhoff.com/content/1033/tcplclib_tc2_mc2/Images/png/9007199325025803__Web.png" width="300">

### 3.3 Library <a name="lib"></a>

To be able to use the above function blocks, it is necessary to add a library. The Tc2_MC2 library contains function blocks to program machine applications.

## 4. Result <a name="R"></a>


## 5. Solution <a name="S"></a>


<br />

*time spent: April 22 to June 3 (6 weeks -> 4 hours * 6 = 24 hours)* <br />
*It took a lot of time because I hadn't controlled a motor via PLC before and because I started from a new project.*
