# DC motor

<img src="https://asset.conrad.com/media10/isa/160267/c1/-/en/001601532PI02/image.jpg" width="250">

## About
The idea was to test this DC motor on the conveyor belt. More specifically, whether the motor was strong enough to run the conveyor belt.

## Materials and methods

- DC motor: Getriebemotor IG320516-FWF22R, 24V, 1:516
- PLC card for the DC motor: EL7332

## Software
[![dc.png](https://i.postimg.cc/Z52GQ2Dp/dc.png)](https://postimg.cc/CRCrBP0x)

Explanation: <br />
Every 5 seconds the direction of rotation will be changed. This is done where we invert the iSpeed. iSpeed is an integer that represents velocity. The range of this value is between -32767 and 32767.

## Result
The DC motor is not strong enough to run the conveyor belt.

## Solution
Use a different (stronger) motor. The stepper motor AS1010-0000 will be tested.
