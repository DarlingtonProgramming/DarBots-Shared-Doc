# Standardization
In order to make usage of Darbots FTC Lib convenient and smoothy, we have published this standardization doc for the purpose of eliminating confusion and accelerating innovation.

## 1.0 Measurement Standardization

### 1.1 Angles

#### 1.1.1 Degrees

**Normalized Degrees**   

The range of normalized degree angles are `[-180, 180)`   

#### 1.1.2 Radians

**Normalized Radians**   

The range of normalized radian angles are `[-2π, 2π)`   

## 2.0 Darbots Coordinate System Standardization

### 2.1 Rotation Standardization

When considering rotations about an axis, consider yourself looking down the (positive) axis of rotation from the positive towards the origin. Positive rotations are then CCW, and negative rotations CW.   


### 2.2 Field Coordinate System

#### 2.2.1 Reference Frame

The reference frame for this definition is the field perimeter wall, adjacent to the RED Alliance Station (known here as the: RED WALL).   
The definition is from the perspective of a person, standing outside the field, in the center of RED WALL, looking towards the center of the field.   

If the Red Alliance Station is ever adjacent to two perimeter walls, the RED WALL will be the one with **most** contact with the Alliance Station.  If the red Alliance Station is ever adjacent to two perimeter walls EQUALLY, then the most clockwise of the two walls will be considered to be the RED WALL.   

#### 2.2.2 Origin

The 0,0,0 origin of the Darbots Field coordinate system is the point in the center of the field, equidistant from all 4 perimeter walls (where the four center tiles meet).   

The origin point rests on the top surface of the floor mat.   

#### 2.2.3 X-Axis

Looking at the origin from the RED WALL, the X axis extends through the origin point and runs to the right and left, parallel with the RED WALL.   

The X axis values increase to the right.   

#### 2.2.4 Z-Axis

Looking at the origin from the RED WALL, the Z axis extends through the origin point and runs out and in, perpendicular to the RED WALL.   

Increasing Z values run out (away) from the RED WALL.   

#### 2.2.5 Y-Axis

Looking at the origin from the RED WALL, the Y axis extends through the origin point and runs up and down in a vertical line.   

Increasing Y values extend upwards.   

#### 2.2.6 Initial Position of a Robot

The Field `(0,0,0)[0,0,0]` Position indicates that the robot is sitting in the center of the field, with its Robot Coordinate System's positive Z direction (Robot Front) pointing in the positive Z direction of the field.   

### 2.3 Robot Coordinate System

#### 2.3.1 Origin

THe (0,0,0) of the Robot Coordinate System is the point in the center of the Robot, equidistant from the very front of the robot and the very back of the robot, as well as equidistant from the very left of the robot and the very right of the robot. The origin always sits on the floor mat.   

#### 2.3.2 X-Axis

Looking at the origin from the very back of the robot, the X axis extends through the origin point and runs to the right and left.   

The X axis values increase to the right.   

#### 2.3.3 Z-Axis

Looking at the origin from the very back of the robot, the Y axis extends through the origin point and runs to the front and back.   

The Y axis values increase to the front.   

#### 2.3.4 Y-Axis

Looking at the origin from the very back of the robot, the Y axis extends through the origin point and runs up and down in a vertical line.   

Increasing Y values extend upwards.   

## 3.0 FTC-Vuforia Coordinate System Definition

### 3.1 Rotation Standardization

Same as Darbots Coordinate System Rotation Standardization.   

### 3.2 Field Coordinate System

#### 2.2.1 Reference Frame

Same as Darbots Field Coordinate System Reference Frame.   

#### 2.2.2 Origin

Same as Darbots Field Coordinate System Origin.   

#### 2.2.3 X-Axis

Same as Darbots Field Coordinate System X-Axis.   

#### 2.2.4 Y-Axis

Same as Darbots Field Coordinate System Z-Axis.   

#### 2.2.5 Z-Axis

Same as Darbots Field Coordinate System Y-Axis.   

#### 2.2.6 Initial Position of a Robot

The Field `(0,0,0)[0,0,0]` Position indicates that the robot is sitting in the center of the field, with its FTC-Vuforia Robot Coordinate System's positive X direction (Robot Front) pointing in the positive X direction of the field.   

### 3.3 Robot Coordinate System

#### 3.3.1 Origin

Same as Darbots Robot Coorinate System Origin.   

#### 3.3.2 X-Axis

Same as Darbots Robot Coordinate System Z-Axis.   

#### 3.3.3 Y-Axis

Looking at the origin from the very back of the robot, the Y axis extends through the origin point and runs to the right and left.   

The Y axis values increase to the left.   

#### 3.3.4 Z-Axis

Same as Darbots Robot Coordinate System Y-Axis.   

## 4.0 Conversion Between two Coordinate Systems

### 4.1 Conversion Between Robot Axis (Used for Phone Position Description Only)
#### 4.1.1 Conversion from Darbots Robot to FTC Robot

`\(x,y,z\)\[rotX,rotY,rotZ\]` => `\(z, -x, y\)\[ rotZ, -rotX, rotY - 90\]`

#### 4.1.2 Conversion from FTC Robot to Darbots Robot

`\(x,y,z\)\[rotX,rotY,rotZ\]` => `\(-y, z, x\)\[-rotY, rotZ + 90, rotX\]`

### 4.2 Conversion Between Field Axis
#### 4.2.1 Conversion from Darbots Field to FTC Field

`\(x, y, z\)[rotX, rotY, rotZ\]` => `\(x, z, y\)\[rotX, rotZ, rotY + 90\]`

#### 4.2.2 Conversion from FTC Field to Darbots Field
`\(x, y, z\)\[rotX, rotY, rotZ\]` => `\(x, z, y\)\[rotX, rotZ - 90, rotY\]`