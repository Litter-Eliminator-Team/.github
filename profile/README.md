# Litter Eliminator Team!

Current Repositories:\
PCB Repo\
ROS Framework Repo\
Machine Learning Repo\
Mechanical Build Repo\

COLLECTIVE MEETING OR BRAINSTORMING HOUR BREAKDOWN:\
Group meeting(1): introductions, discussed general goals and scope -> 1 HR\
Group meeting(2): discussed ROS architecture, and trash retrival mechanism brainstorming -> 1 HR\
Group meeting(3): discussed overall arhitecture and research findings(off the shelf robtics kit including motor controler vs creating custom PCB)  -> 1 HR\
Group meeting(4): discussing 


JAMES FESIK HOUR BREAKDOWN:\
Brainstorming ideas for ROS2 framework, mechanical build, and microcontroller -> 5 HR\
Researching cameras and what camera would be compatible with ROS2 -> 2 HR\
Created the ros2_ws directory in the repo -> 1 HR\
Built and installed the YDLidar SDK repo -> 1 HR\
Built and installed the YDLidar ROS2 Driver and interfaced it with the ros2_ws directory. -> 2 HR\
Built and installed usb_cam ROS2 Foxy Driver package and interfaced it with our camera -> 2 HR\
Tested that the ROS2 Topics from the camera are running as intended -> 1 HR\
PYTHON SCRIPT: Created base ROS2 subscriber python script that subscribes and converts the incoming camera ROS2 topic to usable OpenCV image -> 2 HR\
PYTHON SCRIPT: Edited script to now detect faces based an already given Haar Cascade face detection machine learning model. -> 2 HR\
PYTHON SCRIPT: Edited script to now publish a ROS2 topic whether the camera sees a face or not and draw bounding boxes around the faces in the image -> 2 HR\
Testing script to make sure that when the camera sees a face there will be a data stream from the Raspberry Pi outputting a 1 and vice versa -> 1 HR\
Built and installed the micro_ros library and example code to interface with our RP2040 microcontroller -> 3 HR\
Tested the example publisher code to test if the microcontroller can communicate to the Raspberry Pi 4 using ROS2 topics -> 2 HR\
Making a custom micro_ros script so the microcontroller can subscribe to topics that are being published by the Raspberry Pi. -> 5 HR\
Debugging code and brainstorming power saving issues that we were having with the USB port on the Raspberry Pi 4. -> 6 HR\
Helping with the Machine Learning model to interface with the ROS2 framework already implemented. -> 3 HR\
Trying to integrate detecto, custom haar cascades, and yolov5 machine learning models in ROS framework -> 4 HR\
Helping with the mechanical build team of Michelle and Natalie to debug problems that were occuring. -> 3 HR\
TOTAL HOURS: 47


