<center><a href='https://airscker.github.io/Purple-Micro-Star/' ><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/PMS.png?raw=true'></a></center>

# Document of <a href='https://airscker.github.io/Purple-Micro-Star/doc/Gravitational%20Wave.html'>PurpleMicroStar.GravitationalWave</a>

> Every massive object that accelerates produces gravitational waves.This includes humans, cars, airplanes etc., but the masses and accelerations of objects on Earth are far too small to make gravitational waves big enough to detect with our instruments.
> 
>To find big enough gravitational waves, we have to look far outside of our own solar system. It turns out that the Universe is filled with incredibly massive objects that undergo rapid accelerations that by their nature, generate gravitational waves that we can actually detect. Examples of such things are orbiting pairs of black holes and neutron stars,or massive stars blowing up at the ends of their lives.
> 
> LIGO scientists have defined four categories of gravitational waves based on what generates them:
> 
>- Continuous
> 
>- Compact Binary Inspiral
> 
>- Stochastic
> 
>- Burst
> 
>Each category of objects generates a unique or characteristic set of signal that interferometers can sense,but not all types of Gravitational Wave can be simulated numerically. This module simulate the gravitational wave of *Compact Binary Inspiral Gravitational Wave* and *Continuous Gravitational Wave*
> 
> To get more information about Gravitational Wave, please see [GW-sources, LIGO](https://www.ligo.caltech.edu/page/gw-sources)

## Available Class and Functions:

### **class** `PurpleMicroStar.GravitationalWave.CBIGW()`

#### Compact Binary Inspiral Gravitational Waves
> Compact binary inspiral gravitational waves are produced by orbiting pairs of massive and dense ("compact") objects like white dwarf stars, black holes, and neutron stars.
>
> There are three subclasses of "compact binary" systems in this category of gravitational-wave generators:
>
> - Binary Neutron Star (BNS)
>
> - Binary Black Hole (BBH)
>
> - Neutron Star-Black Hole Binary (NSBH)
>
> Each binary pair creates a unique pattern of gravitational waves, but the mechanism of wave-generation is the same across all three. It is called "inspiral".
>
> Inspiral occurs over millions of years as pairs of dense compact objects revolve around each other. As they orbit, they emit gravitational waves that carry away some of the system's orbital energy. As a result, over eons, the objects orbit closer and closer together. Unfortunately, moving closer causes them to orbit each other faster, which causes them to emit stronger gravitational waves, which causes them to lose more orbital energy, inch ever closer, orbit faster, lose more energy, move closer, orbit faster... etc. The objects are doomed, inescapably locked in a runaway accelerating spiraling embrace.(Comes from [GW-sources, LIGO](https://www.ligo.caltech.edu/page/gw-sources))
>     

##### Parameters:
- **m1,m2**: The mass of planets
- **r1,r2**: The orbit radius of per planets
- **Name**: the name of binary planets
##### Available functions:
`Grav_Wave()`: Get the gravitational wave field
>###### Parameters:
>- Obser_R: the position vector of the observer
>- T_now: the time at the place of observation
>###### Return:
>- The Gravitational Wave Field, in nparray

`Distance()`: Get the derivation of the total energy of starbodies at specified time
>###### Parameters:
>- T_now: the current time, in s
>###### Return:
>- The distance between two celestial bodies

`DEnergy_Loss()`: Get the derivation of the total energy of starbodies at specified time
>###### Parameters:
>- T_now: the current time, in s
>###### Return:
>- Energy loss of Compact Binary Inspiral Gravitational Waves per unit time

`Detect_Signal()`: Get the interferometer strain signal of LIGO
>###### Parameters:
>- Obser_R: the position vector of the observer
>- T_now: the time at the place of observation
>###### Return:
>- The Detected Gravitational Wave Field Signal(scalar)

`Orbit_Phase()`: Get the r1/r2 phase at the specified time, phase=0 when r1 along the x+ axis
>###### Parameters:
>- T_now: the current time, in s
>###### Return:
>- Orbit phase of binary system, in rad

`DATA()`: Plot data of Gravitational wave as well as save the ploted image
>###### Parameters:
>- Dt: the time interval between nearby points
>- T_init: the start time of data
>- T_end: the end time of data
>- Obser_R: the position vector of the observer
>- imgoutput: the folder to save the ploted image, if it's empty, no image will be saved
>- Plot: plot the data curve
>###### Return:
>- Distance,Gravitational wave field strength,Detected signal,Orbit phase, in nparray

### **class** `PurpleMicroStar.CGW()`
#### Continuous Gravitational Waves
>Continuous gravitational waves are thought to be produced by a single spinning massive object like a neutron star. Any bumps on or imperfections in the spherical shape of this star will generate gravitational waves as it spins. If the spin-rate of the star stays constant, so too are the gravitational waves it emits. That is, the gravitational wave is continuously the same frequency and amplitude (like a singer holding a single note). That's why these are called “Continuous Gravitational Waves”.(Comes from [GW-sources, LIGO](https://www.ligo.caltech.edu/page/gw-sources))

##### Parameters:
- **Mass**: the mass of the pulsar
- **Radius**: the radius of the pulsar
- **Spin**: the saclar spin speed of the planet, in rad/s, the spin will be automatically aligned to z-axis
- **Name**: the name of the pulsar
- **Meg**: the megnatic dipole of the pulsar
- **RotI**: the rotation inertia of the pulsar

All parameters meet SI standard.

##### Available functions:
`GWSpin()`: Get the Spin velocity in rad at time T_now, evolve with Gravitational Wave field
>###### Parameters:
>- T_now: the time at the place of observation
>###### Return:
>- The spin velocity of the pulsar

`Distance()`: Get the derivation of the total energy of starbodies at specified time
>###### Parameters:
>- T_now: the current time, in s
>###### Return:
>- The distance between two celestial bodies

`Detect_Signal()`: Get the interferometer strain signal of LIGO
>###### Parameters:
>- Obser_R: the position vector of the observer
>- T_now: the time at the place of observation
>###### Return:
>- The Detected Polarized Gravitational Wave Field, [h+,hx]

`DATA()`: Plot data of Gravitational wave as well as save the ploted image
>###### Parameters:
>- Dt: the time interval between nearby points
>- T_init: the start time of data
>- T_end: the end time of data
>- Obser_R: the position vector of the observer
>- imgoutput: the folder to save the ploted image, if it's empty, no image will be saved
>- Plot: plot the data curve
>###### Return:
>- Spin(scalar, in nparray),Signal(Containing h+/hx polarized element, its shape is (N,2), in nparray)


### **Function** `PurpleMicroStar.GravitationalWave.Reduce_mass()`
##### Parameters:
- **m1,m2**: the mass of two celestial bodies
##### Return:
- The reduced mass of two celestial bodies
### **Function** `PurpleMicroStar.GravitationalWave.Total_E()`
##### Parameters:
- **m1,m2**: the mass of two celestial bodies
- **Distance**: the distance between two celestial bodies
##### Return:
- The total energy of the binary celestial bodies
### **Function** `PurpleMicroStar.GravitationalWave.Orbit_spin()`
##### Parameters:
- **m1,m2**: the mass of two celestial bodies
- **Distance**: the distance between two celestial bodies
##### Return:
- The spin velocity(scalar) of the system of binary celestial bodies
### **Function** `PurpleMicroStar.GravitationalWave.Schwarz_Radius()`
##### Parameters:
- **m**: the mass of the celestial bodies
##### Return:
- The Schwarz Radius of the celestial bodies



Author: Airscker/Yufeng Wang
License: GPL-3.0 License

We go on util we go wrong, then we keep on util we are right.




