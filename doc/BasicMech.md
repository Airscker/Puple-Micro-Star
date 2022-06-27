<center><a href='https://airscker.github.io/Purple-Micro-Star/' ><img src='https://github.com/Airscker/Purple-Micro-Star/blob/Web/imgs/PMS.png?raw=true'></a></center>

# Document of <a href='https://airscker.github.io/Purple-Micro-Star/doc/BasicMech.html'>PurpleMicroStar.BasicMech</a>
## Introduction
This module contains some basic mathematical and physical algorithms

## Available Classes and Functions

### **Function** `G_Force()`: 
Get two planets' gravity force
##### Parameters:
- m1,m2: the mass of two planets
- pos1,pos2: the PCI coordinate position of two planets, in the form of list [x,y,z]
##### Return:
- The gravity force of two planet, in the form of nparray [fx,fy,fz]
- If two planets too close to get result, None is returned

### **Function** `Vec_Project()`: 
Project the 2nd vector to 1st vector
##### Parameters:
- vec1: the vector selected as base, in the form of list [x,y,z]
- vec2: the vector need to be projected, in the form of list [x,y,z]
##### Return:
- The projected vector, in the form of nparray [x,y,z]

### **Function** `AngleXYZ()`: 
Get the angle between the vector and specified plane
##### Parameters:
- plane: 'XY','YZ','XZ' available
##### Return:
- The angle in degree

### **Function** `Vec_Length()`: 
Get the length of vector
##### Parameters:
- vec: a 3-d list/nparray
##### Return:
- The length of the vector

### **Function** `Vec_Norm()`:
Get normalized vector
##### Parameters:
- vec: a 3-d list/nparray
##### Return:
- The normalized vector

### **Function** `Rotate_XYZ()`: 
Rotate vector clockwise
##### Parameters:
- vec: a 3-d list/nparray
- rad: the rotated radius angle
- Axis: the axis rotating around
##### Return:
- The rotated vector




Author: Airscker/Yufeng Wang

License: GPL-3.0 License

We go on util we go wrong, then we keep on util we are right.



