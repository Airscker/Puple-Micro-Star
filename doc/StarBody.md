<center><a href='https://airscker.github.io/Purple-Micro-Star/' ><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/PMS.png?raw=true'></a></center>

# Document of <a href='https://airscker.github.io/Purple-Micro-Star/doc/StarBody.html'>PurpleMicroStar.StarBody</a>

## Introduction
This module is built for simulating single celestial body, as well as calculating basic properties
## Available Classes and Functions:
### **class** `PurpleMicroStar.StarBody.StarBody()`

##### Parameters:
- **Position**: the position of the planet, in PCI coordinate with the form [x,y,z]
- **Velocity**: the velocity of the planet, in PCI coordinate with the form [vx,vy,vz]
- **Mass**: the mass of the planet
- **Radius**: the radius of the planet
- **Spin**: the spin speed of the planet, in rad/s
- **Name**: the name of the planet

All parameters meet SI standard.

##### Available functions:
`Force()`: Get the gravity force of this planet(Multibody gravity force)
>###### Parameter:
>- manybody: the list of other existing planet bodies' Object of StarBody
>###### Return:
>- The Multibody gravity force of this planet

`Iteration()`: Get the motion information of this planet at specified time
>###### Parameters:
>- dt: the time period per motion used
>- iterCount: the iteration times of dt

`Roche_limit()`: Get all starbodies' roche limit proportion
>###### Parameters:
>- manybody: the list of other existing planet bodies' Object of StarBody




Author: Airscker/Yufeng Wang

License: GPL-3.0 License

We go on util we go wrong, then we keep on util we are right.



