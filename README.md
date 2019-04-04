# Self Driving RC Car
A Self-Driving Remote Control Car controlled by the Android browser by using a Raspberry Pi.

## Hardware
* [Remote control car](https://www.amazon.com/RC-Cars-Boy-Gift-Crawlers/dp/B07D2CZ7QF/ref=sr_1_fkmrnull_3?keywords=toyard+rc+car&qid=1554386210&s=gateway&sr=8-3-fkmrnull)
* Raspberry Pi
* [L28N Dual Motor Controller](https://www.amazon.com/Qunqi-2Packs-Controller-Stepper-Arduino/dp/B01M29YK5U/ref=sr_1_2_sspa?crid=3IT1MD6DE13M8&keywords=qunqi+l298n+motor+drive+controller&qid=1554386315&s=gateway&sprefix=qunqi+%2Caps%2C150&sr=8-2-spons&psc=1)
* [Smartphone External Battery](https://www.amazon.com/Anker-PowerCore-Ultra-Compact-High-Speed-Technology/dp/B01CU1EC6Y/ref=sr_1_1?crid=CJHXP0O4LWGF&keywords=anker+powercore+5000&qid=1554386394&s=gateway&sprefix=anker+power+core+%2Caps%2C156&sr=8-1)
* 4x AA batteries

### Hardware Architecture
The remote control car has 2 DC motors, and I used the L298N module to control them. You can see how to do that [here](https://www.youtube.com/watch?v=AZSiqj0NZgU). Both the motors and the L298N module are powered by 4AA batteries. The Raspberry Pi is powered by an external battery and we have also a Pi Camera with it. Finally, There are a few jump wires connecting the GPIO from the PI to the L298N module.

<p align="center">
 <img width="500" src="https://imgur.com/UZy1jFc.jpg">
<p>
 
<p align="center">
 <img width="500" src="https://i.imgur.com/IiQeJpG.jpg">
<p>

## Software

### Software Architecture
The main program buids an Self Driving Car object and starts a WebServer for the remote and camera stream. The car is made of a few parts:

* SelfCar:
  * Handles interaction with the motors for movement and speed
* Camera:
  * Handles camera stream and object detection for the stop sign
* StreamCar:
  * Creates a webserver to stream the camera and control the car
* Train:
  * Handles gathering and saving train data
* CarLearn:
  * Handles the load of the pre-build Machine Learning model and self-driving based on the camera images

### Challenges


### Model training


### Self-driving
The pre-trained model is loaded on the start of the program. Once the command from any browser comes in, a loop starts the self-driving: the process gathers the most recent img, makes the prediction and turns the car.

<p align="center">
 <img width="800" src="">
<p>

### Object detection
The stop sign detection was made using Haar feature-based cascade classifiers. OpenCV have a very comprehensive functions and you can train your own model following tutorials like [this](https://coding-robin.de/2013/07/22/train-your-own-opencv-haar-classifier.html). This approach is good considering it's very fast and we need speed to detect, classify and take action for every single frame. I used a pre-trained classifier from [here](https://github.com/hamuchiwa/AutoRCCar) and it worked very well for my stop sign.

