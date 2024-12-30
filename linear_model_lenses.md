# Goal and Facts
The claim I seek to provide evidence for is:
any spherocylindrical lens ( or a prescription only with spherical and angled cylindrical components) can be thin-lens approximated by 
1. 2 cylindrical lenses whose strength and orientation are a function of the prescription.
2. 3 cylindrical lenses whose strength are a function of the prescription, but the orientations are three sufficiently different angles. 
### Intuition
Cylindrical lenses focus to a line; thus, two orthogonal cylindrical lenses should focus to a point.
## Formula for Optical Power of Compound Lenses made of thin lenses
```P_mix = P_1 + P_2 - d*(P_1)*(P_2) ```
https://en.wikipedia.org/wiki/Lens#Compound_lenses
https://en.wikipedia.org/wiki/Optical_power
So as the distances approach zero the system becomes linear.
## Formula for Power of Sphereocylindrical lens at an angle
```P(theta) = S + C*sin^2(theta+axis) ```
CITATION NEEDED
# Deriving Decomposing Spherocylindrical
## applying formulas to get 1:
```P_target(theta) = S + C* sin^2(theta+axis)```
Use  lens A lined up with the axis and lens B 90 degrees out of phase with the axis.
```P_approximate(theta) = C_A*sin^2(theta+ axis) + C_B *sin^2(theta+axis+90degrees)```
Set power of B equal to S and power of A equal to S+C :
```P_approximate(theta) = (S+C)*sin(theta+axis) + S*sin^2(theta+axis+90degrees) = S*(sin^2(theta+axis) + cos^2(theta +axis)) + C*sin^2(theta+axis) = S + C*sin^2(theta+axis) ```
Simple trigonometry and the small distance/thin lens approximation get us to the conclusion.
### Book on optometry just shows 1:
https://www.aao.org/Assets/327610a9-f1e4-4d7c-90e7-159c479f790e/637151349587270000/bo10-pdf?inline=1
See slides 12 and 13
### Knowledge is old:
See Jackson Cross Cylinder and its history from the early 1800s.
https://en.wikipedia.org/wiki/Jackson_cross_cylinder
## applying formulas to get 2:
```P(theta) = S + C* sin^2(theta + axis) ```
Using trigonometric formula for square of sine.
```P(theta) = S + C/2 + (C/2)*cos(2*theta +2*axis) ```
Using sum of angles formula for cosine:
```P(theta) = S + C/2 + (C/2)*cos(2*theta)*cos(2*axis) - (C/2)*sin(2*theta)*sin(2*axis) ```
We get three linear parts a constant part, a ```cos(2*theta)```, and a ```sin(2*theta)```
As long as the three axises we choose to form our lenses from create an invertible matrix 
when mapping the 3 power basis of those lenses to the constant,sin2theta cos2theta basis.
Then any spherocylindrical lens will be able to be able to be represented by that three axis basis of cylindrical lenses.
This follows from the linear algebra we are using because of thin lens and close distance assumption.

# Remaining known sources of error:
## Thickness and Closeness of Lenses:
We can minimize this source of error via using fresnel like subdividing of the lenses,
while being careful not to let the discontinuities take up too much space in the visual field.
## Spherical distortion
We can minimize this source of error by using extruded cartesian ovals instead of cylinders.
# Open Question:
Is there a remaining notable source of error?

