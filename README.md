See the PDF for now
[smartdesktutorial.pdf](https://github.com/Goteborgsvagen78b1101HA/SmartDesk/files/11991453/smartdesktutorial.pdf)
Smart Home Desk

Tutorial on how to make your electrified standing desk smarter.

In this project we’ll explore the possibilities to interface with a standing desk from a microcontroller (in this tutorial Pico w). We’ll also connect some necessary and some optional sensors for high measurement, temperature, room humidity and light intensity. To make it useful we’ll be sending data over MQTT, displaying data in home assistant and make some automations.
The time estimate for this project is TIME. Distributed as followed:

•	Setting up Home Assistant. \n
•	Setting up local MQTT broker.
•	Setting up HASS.agent.
•	Building the hardware.
•	Program the microcontroller.
•	Creating the dashboard in Home Assistant.

Objective
To me this is a project to make my home office smarter and more automated. I have a motorised standing disk that I barely use. The sun hits my screens in the morning, and the work light is poor during the evenings. To solve this, I’ll make automations to rase the desk if I’m seated for to long. Activate smart blinds to (only) shade my screens and install a led strip over my working area controlled by the desk’s microcontroller.
By doing this project I hope to learn more about programming microcontrollers and create electronics and modify/enhance functionality of existing electronics.

Material
Explain all material that is needed. All sensors, where you bought them and their specifications. Please also provide pictures of what you have bought and what you are using.


----------------------------------------------

You’ll also need an old laptop/computer/IntelNUC to run home assistant and MQTT broker on. And a soldering iron.

Computer setup
The software I used for this project is Thonny as IDE. VS code can de used as well but I had some problems with it not uploading files to the Pico W sometimes with resulted in me running old versions of my program and thinking errors is not salved even thou they were. The language I used and which seams to be the most common for the Pico W is MicroPython. Because the Pico W is new on the market you also need to update the firmware. For this project you also need Home assistant and mosquito (or any other MQTT broker)

Putting everything together
The board contains 2 light resistors to se how light it is in the room. One dht11 sensor for room temperature and humidity. One temperature sensor for in case temperature. One, two way, relay that acts as the buttons on the standing desk. One le-strip of 91 leds. One ultrasonic sensor to determine the current height of the desk

 Pictures xD

To display data and make automations we are using Home Assistant. This is so that it can be built on and added to as you smart home expands. To me this was the only choice since I’m already using it for other things. 

The code

I’m using the _thread lib to utilise both cores in the Pico. One of LEDs and one for everything else, this so that I can run animations on the LED-strip without interrupting other functions. 

