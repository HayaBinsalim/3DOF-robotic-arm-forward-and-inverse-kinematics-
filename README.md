# 3DOF-robotic-arm-forward-and-inverse-kinematics

# Description
In this project, the forward and inverse kinematics of a 3 DOF robotic arm is calculated. The schematic of the arm is shown in the figure below. 

 ![image](https://github.com/user-attachments/assets/be95742a-09e2-4f4e-9663-721a1206bb18)

# Forward Kinematics 
The three variables required for the forward kinematics calculation are: x3, y3, and φ. The equations for these variables are below. 
```
-	Φ =  θ1 + θ2 + θ3
-	x3 = a1 + a2 + a3 
-	y3 = b1 + b2 + b3 
```
#### For the x-axis values: 
```
-	a1 = l1cos(θ1)
-	a2 = l2cos(θ1 + θ2)
-	a3 = l3cos(θ1 + θ2 + θ3)
```
#### For the y-axis values: 
```
-	b1 = l1sin(θ1)
-	b2 = l2sin(θ1 + θ2)
-	b3 = l3sin(θ1 + θ2 + θ3)
``` 
#### Calculations:
In this case, the l1, l2, l3, θ1, θ2, and θ3 values will be assumed: 

-	l1 = 20 ; l2 = 15 ; l3 = 10 
-	θ1 = 30 ;  θ2 = 45 ;  θ3 = 60 

Start by calculating the unknown values using the above equations and the assumed values. 
```
a1 = 20cos(30) = 17.3
a2 = 15cos(30 + 45) = 3.88
a3 = 10cos(30 + 45 + 60) = -7.07

b1 = 20sin(30) = 10
b2 = 15sin(30 + 45) = 14.4
b3 = 10sin(30 + 45 + 60) = 7.07
```
### Forward Kinematics Results: 
-	**x3** = 17.3 + 3.88 + -7.07 = **14.11** 
-	**y3** = 10 + 14.4 + 7.07 = **31.47** 
-	**Φ** = 30 º + 45 º + 60 º = **135º**
  
# Inverse Kinematics 
The inverse kinematics is used to find the angles (θ1, θ2, and θ3) values to reach the desired end-effector position. In this case, the desired position is calculated in the forward kinematics: **(14.11, 31.47)**. 

#### First, find the distance *d* :
```
d = √(x2 + y2) – l3 
= √(14.112 + 31.472) – 10
= 24.48
```
#### For **θ1**: 
```
θ1 = a – b 
a and b are found as follows:
-	a = tan-1(y/x)
    = tan-1(31.47 / 14.11) 
    = 65.85 º

-	b = cos-1( (l12 + d2 – l22) / 2∙l1∙d ) 
    = cos-1( (202 + 24.482 – 152) / (2∙20∙24.48) )  
    = 37.74 
```
**θ1** = 65.85 – 37.64 = **28.21 º**

#### For **θ2**: 
```
θ2 = cos-1( (l12 + l22 – d2) / (2∙l1∙l2) ) 
   = cos-1( (202 + 152 – 24.482) / (2∙20∙15) )
```
**θ2** = **87.54 º**

#### For **θ3**:
```
θ3 = Φ − θ1− θ2
   = 135 – 28.21 – 87.54
   = 19.25 º
```

