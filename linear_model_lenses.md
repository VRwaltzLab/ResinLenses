# Goal and Facts
The claim I seek to provide evidence for is:
any spherocylindrical lens ( or a prescription only with spherical and angled cylindrical components) can be thin-lens approximated by 
1. 2 cylindrical lenses whose strength and orientation are a function of the prescription.
2. 3 cylindrical lenses whose strength are a function of the prescription, but the orientations are three sufficiently different angles.
A Spherical lens can be compound lens approximated by
3. Many cylindrical lenses
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
### Claim The matrix is invertible if the axis are distinct angles in [0,180) degrees
proof: The matrix has ```1/2``` in the top row, and the matrix has ```cos(2*axis)/2``` in the second row for corresponding axis, and likewise ```-sin(2*axis)/2``` in the bottom row.
If we left multiply by a matrix with 2 in the top left corner and (2, -2i; 2, 2i) as the bottom right 2 by 2 matrix and zeros elsewhere,
then we get with 1's in the top row, ```e^(i2*axis)``` in the second row and ```e^(-i2*axis)``` in the third row. (apply trigonometric identity)
This can be right multiplied by a diagonal matrix ```e^(2i*axis)``` to get a permutation of a vandermonde matrix with x_j = e^(2i*axis_j) . (apply exponent addition rules)
By properties of vandermonde matricies, this matrix is invertible if the x_j's are distinct, which holds iff the angles are distinct.
So because we multiplied by clearly invertible matricies, the original matrix was invertible if and only if the angles are distinct.
Warning: if the angles are very close, the matrix might have high condition number and so inverting it might introduce numerical instability.
This would be bad, because large numbers in the output might break the assumptions of thin lenses, and introduce error.
Suggestion: use either 0, 45, 90 or 0, 60,120 for angles that are both easy to reproduce and numerically stable.
## More lenses Case :
In a bad eyesight prescription of -10dpt spherical with an air gap of 1 cm, the compound lens's formula nonlinear term for two orthogonal cylindrical lenses becomes -0.25dpt on the off axis error.
This is prescription wise notable, and so  might need correcting.
In a VR game setting with a +22.22dpt spherical (45mm focal length) this will be notable.
So we need a general construction (which is correct relative to the two formula we are using):
Lens 1 is a pair of cylindrical singlets, 90 degrees out of phase.
Lens i is a pair of lenses i-1, 90/2^i degrees out of phase separated by a standard size gap d.
Note: it is unclear where the d factor should be measured in more compound systems. (probably because the formula isn't intended to be extended too much)
Claim: the nonspherical term of lens i has frequency 2^(i+1) and power proportional to the base power raised to 2^i times all the distance factors.
Base case: ``` P_0 = P_base/2+P_base*cos(2theta)/2 ```
``` P_1 = P_0 + P_0' - d*P_0*P_0' = (P_base/2 + P_base*cos(2theta)/2) + (P_base/2 - P_base*cos(2theta)/2) - d*(P_base/2 - P_base*cos(2theta)/2)*(P_base/2 + P_base*cos(2theta)/2) ```
``` = P_Base -d* P_base^2/4( 1- cos(2theta)*cos(2theta)) = P_base - d*P_base^2/8*(1 + cos(4theta)) ```
Inductive step
using C for all the messy distance and power terms:
```P_i = P_(i-1) + P_(i-1)' - d*P_(i-1)'*P_(i-1)' = (P + C*cos(2^(i-1)theta) ) + (P - C*cos(2^(i-1)theta) ) - d*(P + C*cos(2^(i-1)theta) )* (P - C*cos(2^(i-1)theta) )```
```=2P - d*P*P + d*C*C(cos(2^(i-1)theta) )^2 = 2P - d*P*P +d*C*C - d*C*C*sin^2(2^(i-1)theta) = 2P -d*P*P +d*C*C/2 -d*C*C/2*cos(2^i theta) ```
I believe the asymptotics here follow from the formula, but I do not know if the formula survives this level of compounding lenses.

# Remaining known sources of error:
### Thickness and Closeness of Lenses:
We can minimize this source of error via using fresnel like subdividing of the lenses,
while being careful not to let the discontinuities take up too much space in the visual field.
### Spherical distortion
We can minimize this source of error by using extruded cartesian ovals instead of cylinders.
### Glasses Error:
Eye Rotation with static glasses might create errors that occur on the edges of vision.
# Open Question:
Is there a remaining notable source of error?

