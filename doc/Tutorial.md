<center><a href='https://airscker.github.io/Purple-Micro-Star/' ><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/PMS.png?raw=true'></a></center>

# Simple Tutorial of PurpleMicroStar
This is just a simple tutorial about how to use this project quickly, and if you want to get the hang of this project totally, please refer to the document of our project.
## Multibody Motion Curve
```python
import PurpleMicroStar.MultiBody as MB
# Create Multibody Object
mb1=MB.MultiBody()
# Load Multibody information
mb1.Dataset(datapath=os.path.join(PurpleMicroStar.__path__[0],'exampledata\\Multibody-3.csv'))
# Print Multibody information
print(mb1)
```
Util now we get this :

```
---Basic Information of Multibody---

  Name             x           y           z            vx  ...          Mass       Radius  sx  sy       sz
0  SA1 -9.564347e+10 -9955225453 -8469093529 -17966.682980  ...  2.900000e+24  4020253.678   0   0  0.00008
1  SA2  6.115327e+09 -7445764970  1691166738   8629.030680  ...  6.700000e+24  4626639.025   0   0  0.00008
2  SA3  3.410000e+11  3019611419  9134125314   2358.759086  ...  4.800000e+24   232300.352   0   0  0.00008

[3 rows x 12 columns]
```

And then we iterate the motion curve and plot it:

```python
# Iteration
mb1.Iteration(dt=100,iterCount=1e5,output='C:\\MultiBody-CurveData')
# Plot
mb1.Plot()
```
At the end we get these things:

<center><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/mb1.png?raw=true'></center>

This image is the 3d curve of the Multibody system, you can create more complex and more beautiful multibody systems!

And the curve data files are stored in `'C:\\MultiBody-CurveData'`:

<center><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/curve.jpg?raw=true'></center>

you can rebuild this Multibody system by using `mb1.Rebuild()`, and more detailed information please refer to [Document of MulityBody](https://airscker.github.io/Purple-Micro-Star/doc/MultiBody.html)

## Building StarBody
This is the most simple but the most important module of whole project, we calculate all celestial data based on basic StarBody. So how to build it?
```python
import PurpleMicroStar.StarBody as SB
# Build StarBody
sb1=SB.StarBody()
# Print information of it(using default configuration)
print(sb1)
```
Now we get these things:

```
---Basic Information of the StarBody Earth---

+----------------------+---------------------------------+
|      Properties      |              Value              |
+----------------------+---------------------------------+
|     Position(m)      |             [1 1 1]             |
|    Velocity(m/s)     |       [10000 10000 10000]       |
|       Mass(kg)       |            5.965e+24            |
|    Density(kg/m3)    |        5535.4188936586015       |
|      Radius(m)       |            6360000.0            |
| Spin Velocity(rad/s) | [0.000e+00 0.000e+00 7.292e-05] |
|   Gravity Force(N)   |            [0. 0. 0.]           |
| Time Since Launch(s) |                0                |
|   Iteration Times    |                0                |
+----------------------+---------------------------------+

---Advanced Properties of the StarBody Earth---

+------------------------------+-----------------------+
|          Properties          |         Value         |
+------------------------------+-----------------------+
|   1st order velocity(m/s)    |   7910.863415852705   |
|   2nd order velocity(m/s)    |   11187.650332780044  |
|    Roche limit proportion    |          0.0          |
|          Black Hole          |         False         |
|       Vision Radius(m)       |  0.004428569680782358 |
| Maximum Spin Velocity(rad/s) | 0.0012438464490334442 |
+------------------------------+-----------------------+
---More are available because of your exploration! And all properties meet SI standard---
```
## Gravitational Wave

>Every massive object that accelerates produces gravitational waves.This includes humans, cars, airplanes etc., but the masses and accelerations of objects on Earth are far too small to make gravitational waves big enough to detect with our instruments.
>
>To find big enough gravitational waves, we have to look far outside of our own solar system. It turns out that the Universe is filled with incredibly massive objects that undergo rapid accelerations that by their nature, generate gravitational waves that we can actually detect. Examples of such things are orbiting pairs of black holes and neutron stars,or massive stars blowing up at the ends of their lives.
>
>LIGO scientists have defined four categories of gravitational waves based on what generates them:
>
>- Continuous
>
>- Compact Binary Inspiral
>
>- Stochastic
>
>- Burst
>  Each category of objects generates a unique or characteristic set of signal that interferometers can sense,but not all types of Gravitational Wave can be simulated numerically. This module simulate the gravitational wave of **Compact Binary Inspiral Gravitational Wave** and **Continuous Gravitational Wave**.
>
>To get more information about Gravitational Wave, please see [GW-sources, LIGO](https://www.ligo.caltech.edu/page/gw-sources)

### Compact Binary Inspiral Gravitational Wave:
```python
import PurpleMicroStar.GravitationalWave as GW

# Create binary system using default parameters
bsh1=GW.CBIGW()
# Print key information of binary system
print(bsh1)
```
Then we get these things:

```
---Basic information of Binary Celestial Body System---

 +------------------+------------------------+--------------------------+
| Name of Planets  | Mass of Planets(M_Sun) | Initial Orbit Radius(AU) |
+------------------+------------------------+--------------------------+
| Celestial Body 1 |         200.0          |          1e-05           |
| Celestial Body 2 |         1000.0         |          2e-05           |
+------------------+------------------------+--------------------------+

Total coalescence time: 342.0156938987459s
Current time of the system: 0s

---More Properties are waiting for your exploration!---
```

And then we can calculate the whole available data and plot them as this:

```python
bsh1.DATA()
```



<center><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/CBIG.jpg?raw=true'></center>

Similar to Binary Celestial Bodies, the Continuous Gravitational Wave can be calculated in this way:

```python
cw1=GW.CGW()
cw1.DATA()
```

we get this:

<center><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/pulsar.png?raw=true'></center>




Author: Airscker/Yufeng Wang

License: GPL-3.0 License

We go on util we go wrong, then we keep on util we are right.



