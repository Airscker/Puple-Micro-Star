<center><a href='https://airscker.github.io/Purple-Micro-Star/' ><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/PMS.png?raw=true'></a></center>

# Document of <a href='https://airscker.github.io/Purple-Micro-Star/doc/MultiBody.html'>PurpleMicroStar.MultiBody</a>

## Introduction

<center>This module is built for Multibody motion simulation</center>

## Available Classes and Functions:

### **class** `PurpleMicroStar.MultiBody.MultiBody()`:
Buid a cluster of planets, allow they evolution via time and store their Astrophysics properties

##### Parameter:
- **manybody**: a list of **Starbody** Objects(**StarBody**, please see [PurpleMicroStar.StarBody](https://airscker.github.io/Purple-Micro-Star/doc/StarBody.html))

##### Optional operation:
- You can build your new cluster via `Dataset()`, more information please refer to function `Dataset()`
- And you can rebuild your former cluster stored in some files, more information please refer to function `Rebuild()`

##### Available functions:
`Iteration()`: Calculate all planets' motion properties, as well as their body properties, then save them into files
>###### Parameters:
>- dt: the time period per motion used
>- iterCount: the iteration times of dt
>###### Return:
>- Pos_curve: The position information of every planet in every iterated time, in the form of nparray
>	[[[p1_t1],[p2_t1],[p3_t1]],
>	[[p1_t2],[p2_t2],[p3_t2]],...],shape=(iter,body_num,3)
>- Vel_curve: The velocity information of every planet in every iterated time, in the form of nparray
>	[[[v1_t1],[v2_t1],[v3_t1]],
>	[[v1_t2],[v2_t2],[v3_t2]],...]

`Dataset()`: Load MultiBody From Given formated Dataset .csv file
>###### Parameters:
>- datapath: the .csv data root path of planets' basic data
>- datasep: the seperation of every information
>###### Columns' name:  
>- Name,x,y,z,vx,vy,vz,Mass,Radius,Spinx,Spiny,Spinz
>- If you don't obey this rule, the result may boom
>###### Return:
>- The list of Object **Starbody**

`Rebuild()`: Rebuild your planet cluster using data files saved by `Iteration()`, make sure you haven't changed anything of these data, you just need to find the cooresponding filenames

>###### Parameters:
>- body: the $body_Rebuild.csv path
>- position: the $Position.csv path
>- Velocity: the $Velocity.csv path
>###### Return:
>- The list of position curve data, The list of the velocity curve data, The list of Object **StarBody**

`Plot()`: Plot the motion curve of Multibodies





Author: Airscker/Yufeng Wang

License: GPL-3.0 License

We go on util we go wrong, then we keep on util we are right.



