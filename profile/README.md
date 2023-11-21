# Litter Eliminator Team!

Current Repositories:\
PCB Repo\
ROS Framework Repo\
Machine Learning Repo\
Mechanical Build Repo\

The Litter Eliminator Pro (LEP) is a robot that autonomously navigates its environment and recognizes whenever a piece of trash enters its field of vision. Once it recognizes this trash, it will use a retrieval method similar to a brush and dustpan to pick up the trash, and a ramp that behaves as the dustpan will be lifted up to have the trash slide into the container used for storing trash. Trash detection is accomplished via a neural network model coded in Python. Autonomous navigation is achieved using simultaneous localization and mapping (SLAM). An Intel RealSense camera will be used to provide live images to the ML model. A laptop sitting wirelessly on the chassis processes the ML model, SLAM, and runs the ROS architecture. The output of the ML model and SLAM together is sent to the Teensy 4.1 microcontroller. The Teensy uses these signals to move the DC motors and servo motors. For the DC motors, the Teensy must pass the signal to an Adafruit Featherwing over I2C. The servo motors are directly controlled by a PWM pin from the Teensy.

# Dependencies
  
# Starting Code

To start the robot, the laptop first needs to be on and connected to a network. An SSH connection will be used to start the robot wirelessly. Before this make sure all connections are in place. Lift the top of the orange case and plug in a micro USB to the Teensy. Then connect the Teensy and camera USB to the laptop on the robot. If autonomous navigation is wanted, plug the Lidar into the laptop as well. Finally, connect the servo motors to the 3-pin female headers with matching ground on the PCB. Then connect the 6-pin DC motor connections to the correct place on the PCB with ground pins lined up. If connections are flipped simply switch the wrong connections with grounds still in the right positions.

Once the laptop is on and another computer is also connected to the same network use this SSH command:

HERE

Then to start the robot run this command:

HERE

The expected result is the robot continually turning and searching for trash to pick up. 



