# Self Driving RC Car
A Self-Driving Remote Control Car controlled by the Android browser by using a Raspberry Pi.

## Hardware
* [Remote control car](https://www.amazon.com/RC-Cars-Boy-Gift-Crawlers/dp/B07D2CZ7QF/ref=sr_1_fkmrnull_3?keywords=toyard+rc+car&qid=1554386210&s=gateway&sr=8-3-fkmrnull)
* Raspberry Pi 3 Model B+
* [L28N Dual Motor Controller](https://www.amazon.com/Qunqi-2Packs-Controller-Stepper-Arduino/dp/B01M29YK5U/ref=sr_1_2_sspa?crid=3IT1MD6DE13M8&keywords=qunqi+l298n+motor+drive+controller&qid=1554386315&s=gateway&sprefix=qunqi+%2Caps%2C150&sr=8-2-spons&psc=1)
* [Smartphone External Battery](https://www.amazon.com/Anker-PowerCore-Ultra-Compact-High-Speed-Technology/dp/B01CU1EC6Y/ref=sr_1_1?crid=CJHXP0O4LWGF&keywords=anker+powercore+5000&qid=1554386394&s=gateway&sprefix=anker+power+core+%2Caps%2C156&sr=8-1)
* 4x AA batteries

### Hardware Architecture
The remote control car has 2 DC motors, and we used the L298N module to control them. Both the motors and the L298N module are powered by 4AA batteries. The Raspberry Pi is powered by an external battery and we have also a Pi Camera with it. Finally, There are a few jump wires connecting the GPIO from the PI to the L298N module.

<p align="center">
 <img width="500" src="https://imgur.com/kwHJBE2.jpg">
<p>

<p align="center">
 <img width="500" src="https://imgur.com/UZy1jFc.jpg">
<p>


## Software

### Software Architecture
The main program buids an Self Driving Car object and starts a WebServer for the remote and camera stream. The car is made of a few parts:

* SelfCar:
  * Interacts with motor and controls car speed.
* Camera:
  * The code to make the Camera realize the stop sign / Obstacles.
* StreamCar:
  * Creates a server so the phone can connect to the browser and operate the car.
* Train:
  * Gathers train data.
* CarLearn:
  * Handles the Machine Learning model in Keras+ and the images from the camera to make the car self driving.

### Challenges


### Model training


### Self-driving


### Object detection


