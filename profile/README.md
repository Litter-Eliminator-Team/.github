# Litter Eliminator Team!

Current Repositories:\
PCB Repo\
ROS Framework Repo\
Machine Learning Repo\
Mechanical Build Repo\

COLLECTIVE MEETING OR BRAINSTORMING HOUR BREAKDOWN:\
Group meeting(1): introductions, discussed general goals and scope -> 1 HR  
Group meeting(2): discussed ROS architecture, and trash retrival mechanism brainstorming -> 1 HR  
Group meeting(3): discussed overall arhitecture and research findings(off the shelf robtics kit including motor  
controler vs creating custom PCB)  -> 1 HR  
Group meeting(4): discussed trash retrival mechanism again(finalized to use in prototype)  -> 1 HR  
Group meeting(5): chasis was brought in, discussed how other components will fit with it -> 1 HR  
Group meeting(6): suitible microcontroller with motorcontrollers found(finilized to use in prototype -> 1 HR  
TOTAL COLLECTIVE HOURS: 6  


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
TOTAL HOURS: 47 + 6 collective = 53

NICHOLAI PLATONOFF HOUR BREAKDOWN:  
General Preliminary research/Speaking with ML professor -> 3 hours  
Research pytorch documentation -> 1 hour  
Research detector documentation -> 1 hour  
Complete Basic excercises using detector -> 4 hours  
Research Hypergator functionality -> 2 hours  
  
Thursday April 6th: Discussed with Natlie and Michele suitible items for trash retrival, then found and collected sample trash items from home -> 1 hour  
Monday April 10th: Created training data for ML model on three sample objects(took pictures).  
Roughly 300 images per object = 900 total images ~ 2 hours  
  
Tuesday April 11th: More research on Hypergator: How to create custom python environment inside,  
only preset collections of libraries were initially avaliable. These presets did not include the dependencies for Detecto.  
After attempting to set up, custom environment would fail to load and package installs were in wrong directory    -> 2 hours  
  
Tuesday April 11th: Recieved help from Machine Learning professor to properly setup custom  
environment on HyperGator.  -> 1 hour  

Wednesday April 12th: Attempted to train simple ML using one class( bottle cap).  
Debugged library code: problem with cv2.rectangle(). In current version Detecto developer's  
code passed coordinates of vertices of rectangle as floats instead of int type. Casting cordinate to int solved problem.  
After fix, model was able to be trained and a test image was correctly classified. Also, a test video passed performance test(output video was   
written with bounding boxes drawn around cap). -> TOTAL: 4 hours  

Thursday April 13th: Attempted to integrate Detecto model onto Raspberry PI: failed. The Detecto library failed to be imported due to dependencies conflict. 
Attempted to fix dependency issues by downgrading dependencies and trying to create a virtual environment: still failed. Developer documentation of Detecto  
is poor: requirments file(list of pyhon packages) included, but do not specify package versions.  
James discoverd through installing Micro-ROS, the Raspberry PI has an ARM processor. Detecto was not compatible with ARM ubuntu: Detecto ABANDONED  
-> TOTAL: 3 hours  
  
Thursday April 13th: New reasearch on Haar Cascade ML model. Looked for tutorials and guides. Concluded it was most likely sufficient -> 1 hour  
Thursday April 13th: Repurposed training images from Detecto. Trained Haar Cascade model on the bottle cap images. -> 2 hours  
  
Thursday April 13th: Attempted to deploy Haar Cascade model on Raspberry Pi: Failed. Conducted further reasearch to understand why. Found that I needed more
training samples, specifically negative images(images that do not contain the target). Second Model was trained and deployed: failed. After further research
found that Haar Cascade is best for larger objects with distinct features(best is faces). The model uses geometry of the images to determine features. A small circular bottle cap will always perform poorly using Haar Cascade unless many training images are given(greater or equal to 1000 images). 
Haar Cascade : ABANDONED -> 3 hours
  
Friday April 13th: Revisted Haar Cascade using a different piece of trash(has more distinct features). Trained 2 models with multiple iterations. First model: FAILED. The second model with 500 pictures of the broken toy and 300 negatives(without trash) performed PASSABLY. Time includes the taking of the new pictures and adding more pictures of the second model(first model did not have enough images). Time also includes debugging the model by changing parameters: sometimes the model would fail to run.  
TOTAL -> 5 hours.  
Friday April 13: Reasearch into a different ML framwork because Haar Cascasde will likely be an insufficient model for the final build(Design 2). Yolov5 ML model was found -> 1 hours  

Sunday April 15th: Further reasearch on YoloV5 ML framework. A comprehensive guide was found. -> 1 hour

Monday April 16th: Loaded YoloV5 into HyperGator. Created new environment for it to live in. Needed to debug the dependencies, library was failing to call the train method. -> 2 hours

Tuesday April 17th: Trained a YoloV5 model using the bottle cap images. Reasearched and attempted to export the model into an environment similar to Raspberry PI. I 
was struggling to perform infrence(draw bounding box) using the created model. Further reasearch into Yolov5 and Tensflow objects is required: WORK IN PROGRESS
-> 4 hours

GRAND TOTAL: 43 + 6 = 49 HOURS

JORGE OTERO HOUR BREAKDOWN:

4/04 - Discussed how many motors we would be using in total to decide what motor controller would work best from the ones I researched. -> 3 hours

4/05 - Did further research on the Cytron Maker Pi RP2040 and then decided with the group that the Maker Pi would best fit our needs. -> 3 hours

4/07 - Researched ways to program the Maker Pi, which included  C, C++, CircuitPython and MicroPython-> 4 hours

04/09 - Decided that CircuitPython would be the best to program the Maker Pi and downloaded the most recent stable release of the uf2 file for it from the CircuitPython website. I also began reading through how to write CircuitPython code -> 5 hours

4/10 - Downloaded the recommended Python code editor called Mu to write CircuitPython code. I also received the Maker Pi from the mail, which had a link to a github repository that I started to read through (Link: https://github.com/CytronTechnologies/MAKER-PI-RP2040). ->3 hours

4/11 - Discussed the exact connections that would be made between the Maker Pi and the motors, which include 2 DC motors and 4 servo motors, as well as how the Raspberry Pi would connect to the Maker Pi. -> 4 hours

4/12 - Confirmed that the Maker Pi is able to connect to the DC motors, as well as power two of them at the same time. I also confirmed that the Maker Pi can worked with the servo motors that we will be using, which included writing basic code that was based on the code found in the github repository. - 3 hours

4/13 - Had to abandon using CircuitPython due to micro-ROS not being compatible with Circuitpython. I researched if there was any way to still use CircuitPython, but could not find anything. Started to research how to program the Maker Pi with C/C++. -> 4 hours

4/14 - Found out that the Maker Pi can be programmed the same way as the Raspberry Pi Pico, which was discussed in the drivers for embedded systems lab. Experimented with the blink.c file that was provided in the pico_examples directory when doing the lab to see how to power the DC motors in C/C++. Found a youtube video that provided example code for powering servo motors on the raspberry pi pico, which I adapted for the Maker Pi (Link: https://youtu.be/fCIFYKFNcGc). -> 5 hours

4/16 - Wrote a hard coded script that emulates the autonomous behavior of the Litter Eliminator when picking up trash with the press of a button that was labeled as GP20 on the Maker Pi. Fine tuned the angles and acceleration of the servo motors to best suit picking up trash, which involved testing with Natalie. -> 6 hours

GRAND TOTAL: 40 hours + 6 hours = 46 hours


