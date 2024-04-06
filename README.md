# Tangible HCI
This repository contains documentation and code related to Tangible Human-Computer Interaction (HCI) for CPSC 601.04 at the University of Calgary.


## Assignment 0


**Title**: Joe The LED


**Description**: In this Assigment you can interact with an led and read the story of it. The interaction beween to user and the LED is happen by a push button. By pressing that button you can wake up the LEd and ... (He is angry !)


**Image of the Assignment**:


![tempImagejEiC6U](https://github.com/NamiMod/Tangible-HCI/assets/60979433/da95f3d7-b45f-464c-81fb-bc5ec4423690)


![circuit](https://github.com/NamiMod/Tangible-HCI/assets/60979433/821a5c73-f7d8-4c8b-b23a-12fdcddcdb66)


**Result of the Interaction with the LED**:


<img width="1144" alt="Screenshot 2024-01-25 at 11 53 58" src="https://github.com/NamiMod/Tangible-HCI/assets/60979433/3541de31-94f8-428a-8bad-a77c1314369d">

**Video of the Assignment**:


https://github.com/NamiMod/Tangible-HCI/assets/60979433/3d6af2ea-97fd-4617-826b-53c751ff3307



**You can find the arduino code insilde the folder A0 on this repository**


**References**:


1 - Arduino Documentation (https://docs.arduino.cc/built-in-examples/digital/Button/)


## Assignment 1


**Title**: Chaloos, A New Musical Instrument


**Description**: In this assignment, I built a new musical instrument based on a simple trumpet. Essentially, with a basic trumpet, we can produce music by manipulating our mouth, and the trumpet amplifies the sound. Personally, whether I'm working or free, I often play music in my mind or use my mouth. Additionally, I tap on a table or surface to create a beep-like sound in the background.


The idea struck me: what if we added a second background beep-like sound while singing with our mouth using a trumpet? Upon researching this concept, I discovered that blowing air into the trumpet increases the humidity level inside. The idea of playing a beep sound based on the humidity level emerged, and I constructed this instrument. I integrated a humidity sensor inside the trumpet to measure the humidity level. I transmit this data to a Python program using the Serial protocol.


In the Python program, there's a function to generate a beep sound based on the humidity level. I experimented with different formulas to convert humidity levels into the frequency of the output sound. The final formula is present in the Python code. After generating the sound, I play it as a beep to create a background drum-like sound while playing the trumpet.


Additionally, there's a fan that the player can activate briefly using a touch sensor. This helps reduce humidity inside the trumpet, allowing for lower frequencies in the output beep sound.


You can find the generated tone function here


<img width="435" alt="Screenshot 2024-02-13 at 18 02 48" src="https://github.com/NamiMod/Tangible-HCI/assets/60979433/e7063d49-c2f0-43fd-be9d-6f889ad4ed50">

The crucial aspect of the Python code is that there is a thread continuously running the playing sound function while simultaneously listening to the serial port. When a new humidity value arrives, I employ a locking system to pass the updated humidity value to the thread responsible for playing the sound. In this case, everything happens concurrently.


<img width="508" alt="Screenshot 2024-02-13 at 18 59 20" src="https://github.com/NamiMod/Tangible-HCI/assets/60979433/6a130543-eaaf-4e35-a99a-05907a72e04f">


The Arduino code also reads the humidity level using the DHT library and checks the touch sensor. If the user touches the touch sensor, the Arduino will run the fan for two rounds, thereby decreasing the humidity level inside. Additionally, the Arduino code sends the humidity value to the Python code using the serial protocol. You can see the arduino code here:


<img width="360" alt="Screenshot 2024-02-13 at 19 03 06" src="https://github.com/NamiMod/Tangible-HCI/assets/60979433/b6403806-f965-4e29-9cd8-fbdbdf6046d4">

To sum up, with this instrument, I am mapping the level of humidity to sound. By increasing the humidity level based on a formula, I elevate the frequency of the output, and vice versa. Players can also draw upon their previous experience with music, as it functions like a regular trumpet with an additional background sound that the player can control, allowing for the simultaneous production of two sounds.


Regarding the formula for converting humidity to frequency, I experimented with various approaches, and the final formula is satisfactory to me. I also paid attention to the details of the embodiment, such as finding an appropriate place for the touch sensor, as well as positioning the humidity sensor and fan. Placing the humidity sensor at the first part of the trumpet ensured accurate detection of humidity increases, as it was in close proximity to the mouth.


Concerning the fan, if positioned vertically, it would diminish the trumpet's output and increase humidity levels in the middle, as it directs air against the natural flow in the trumpet. These details have been carefully considered in this implementation.



**Image of the Assignment**:


![IMG_4973](https://github.com/NamiMod/Tangible-HCI/assets/60979433/47d8cbc1-ea51-45ba-a8a8-5fc646430023)


![IMG_4972](https://github.com/NamiMod/Tangible-HCI/assets/60979433/2e02c0ba-ed4c-4162-a7ca-bc9e364cbd77)


![IMG_4971](https://github.com/NamiMod/Tangible-HCI/assets/60979433/bbe0e640-8260-4556-91e2-414460215c62)


![IMG_4970](https://github.com/NamiMod/Tangible-HCI/assets/60979433/69e02711-fe62-407e-86a7-205dc4a9c3f5)


**Video of the Assignment**:


https://github.com/NamiMod/Tangible-HCI/assets/60979433/ffa20d20-68fe-4864-9f70-e291375cdaeb


**You can find the arduino code insilde the folder A1 on this repository**


**References**:


1 - Arduino Documentation - Servo ([link](https://docs.arduino.cc/learn/electronics/servo-motors/))


2 - Arduino Documentation - Touch Sensor ([link](https://projecthub.arduino.cc/hibit/using-touch-sensor-with-arduino-83b957))


3 - Arduino Documentation - DHT11, Humidity Sensor ([link](https://projecthub.arduino.cc/arcaegecengiz/using-dht11-12f621))


4 - Arduino Documentation - Serial Communications with Python Program ([link](https://projecthub.arduino.cc/ansh2919/serial-communication-between-python-and-arduino-663756))


5 - Stackoverflow - Generate a tone in python ([link](https://stackoverflow.com/questions/56592522/python-simple-audio-tone-generator))



## Assignment 2


**Title**: Angry? Eat Chocolate!


**Description**: For this project, we have to collect real-world data and visualize it. While brainstorming for ideas, I thought about a fun concept: giving chocolate to angry people to help them calm down! :)


I came up with a cardboard box that people can punch when they're upset. After a certain number of punches, the box gives them a chocolate treat. To count the punches, I used a sensor on the top of the box that measures the distance from top to bottom. When someone punches the box, the distance decreases, and I can detect it as a punch.


The box has three lights: green, yellow, and red. When there are fewer than 4 punches, the green light turns on. Between 4 and 10 punches, the yellow light comes on. After 10 punches, the red light lights up, and a motor moves the chocolate from inside the box to outside, so the person can grab their chocolate reward.


as for the code part, at first I just define all the necessary pins and also setup the servo.


![Screenshot 2024-03-12 at 15 18 30](https://github.com/NamiMod/Tangible-HCI/assets/60979433/48996021-f757-4a18-ae40-5369d9c3ba15)



In the loop part, I'm simply reading and calculating the distance using the sensor's information. After the distance calculation, I check it against a threshold. If the distance is lower than the threshold, I count it as a punch. Based on the number of punches stored in "anger_counter," I can turn the LEDs on or off and initiate the servo rotation. Overall, with this method, I can tally the punches and reward the angry user with chocolate!


![Screenshot 2024-03-12 at 15 18 56](https://github.com/NamiMod/Tangible-HCI/assets/60979433/153c75c1-16db-4d53-8188-3ba3356263a5)


You can see the images of the box and also the circuit in the following pictures.


**Images of the Assignment**:


![IMG_5694](https://github.com/NamiMod/Tangible-HCI/assets/60979433/b51a3c91-ffd9-4bf8-b0e0-57f3842279f8)


![IMG_5695](https://github.com/NamiMod/Tangible-HCI/assets/60979433/b39a6854-419b-4c99-acd6-af63d607a7f8)


![IMG_5696](https://github.com/NamiMod/Tangible-HCI/assets/60979433/96c0d3cf-ed27-4243-a5ae-c3159611068e)


![IMG_5697](https://github.com/NamiMod/Tangible-HCI/assets/60979433/7a6f1cd0-0ef0-4352-b417-abd1f0e79fd1)

![4f56ae59-5741-47c9-b193-ca31a528038f](https://github.com/NamiMod/Tangible-HCI/assets/60979433/26a26dd3-1b11-4110-bf3a-e5c4df84e4ce)


![3892fe4c-2f45-4f9e-b2f1-b59db08cee22](https://github.com/NamiMod/Tangible-HCI/assets/60979433/e082888a-70b6-4b83-a8ee-8991f8e43cba)


![circuit](https://github.com/NamiMod/Tangible-HCI/assets/60979433/3856d743-08bd-4e6a-9784-651c3d7e7989)



**Video of the Assignment**:




https://github.com/NamiMod/Tangible-HCI/assets/60979433/da84b248-addd-42f4-96be-8fb41c76f9e7




**You can find the arduino code insilde the folder A2 on this repository**


**References**:


1 - Arduino Documentation - Servo ([link](https://docs.arduino.cc/learn/electronics/servo-motors/))


2 - Arduino Documentation - HC-SR04 Ultrasonic sensor ([link](https://projecthub.arduino.cc/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-7cabe1))


3 - Arduino Documentation - RGB Led ([link](https://projecthub.arduino.cc/semsemharaz/interfacing-rgb-led-with-arduino-b59902))


5 - Arduino Documentation - Blink ([link](https://docs.arduino.cc/built-in-examples/basics/Blink/))


## Assignment 3


**Title**: Angry? Eat Chocolate! (Version 2.0)


![giphy](https://github.com/NamiMod/Tangible-HCI/assets/60979433/b5a26a6d-3a57-4038-978a-4f6a12e5c35e)


**Description**: For this project, we have to collect real-world data and visualize it. While brainstorming for ideas, I thought about a fun concept: giving chocolate to angry people to help them calm down! :)


![giphy-3](https://github.com/NamiMod/Tangible-HCI/assets/60979433/b0df9fbb-fc8d-4995-b425-8c494a23a498)


I've devised a cardboard box for people to punch when they're upset. After a certain number of punches, the box dispenses chocolate. To tally the punches, I installed a sensor on the box's top that measures the distance from top to bottom. When someone punches the box, the distance decreases, allowing me to detect it as a punch. In this version, there's a Python program communicating with an Arduino using the serial protocol. Now, we can enjoy improved text and audio output instead of just LEDs. The Arduino sends the punch count to the Python program, which triggers different responses based on the number of punches. These responses include: 'It's good to chill and enjoy life and the nice weather!', 'Okay, okay, let's all just chill!', and 'Chill out! Have some chocolate!


Another improvement I've made for this box is enhancing the punch counting system. We now have two sensors instead of one, and these sensors utilize an improved formula to convert their data into real-world distances more accurately. Having two sensors offers several benefits. For instance, I can now detect punches more precisely by monitoring two distances simultaneously. Another advantage is that if one sensor becomes disconnected, the system can still function without counting it as a punch.


Another improvement with this box relates to its build quality. The anger box shouldn't be beautiful, as then no one wants to punch it! Instead, it should be strong enough. Therefore, I opted for a stronger cardboard box this time. Additionally, all the wires are now fixed and attached securely, making disconnection not so easy. Furthermore, I've implemented some software features to ensure functionality even if one sensor becomes disconnected..


The final improvement involves the chocolate dispensing system. In the previous version, I simply attached the chocolate to the servo, and by spinning it, the chocolate moved to the outside of the box. In this version, I've attached a stick to the servo, which, when spun, pushes the chocolates to the outside of the box. With this mechanism, we can now dispense more than one chocolate at a time!

In summary, the following are the list of improvements:

1- Improved and more accurate formula for converting sensor data to distance.
2- Addition of a second distance sensor for better punch counting.
3- Implementation of text and audio outputs instead of three LEDs.
4- Integration of a Python program connected to Arduino using serial communication to display outputs.
5- Enhancement of the chocolate dispensing mechanism.
6- Strengthened wire connections and overall improved build quality


![giphy-2](https://github.com/NamiMod/Tangible-HCI/assets/60979433/bfe3a7ac-309d-4791-b4b2-4cd0d23c5491)


As for the code part, at first I just define all the necessary pins and also setup the servo. In the loop part, I'm reading and calculating the distance using the sensor's information. After the distance calculation, I check it against a threshold. If the distance is lower than the threshold, I count it as a punch. Based on the number of punches stored in "anger_counter," I can show different outputs and initiate the servo rotation. Overall, with this method, I can count punches and reward the angry user with chocolate!


<img width="418" alt="Screenshot 2024-04-06 at 12 12 11" src="https://github.com/NamiMod/Tangible-HCI/assets/60979433/c7c82e72-3779-4bc6-b0bd-44e21d18aa75">


You can see the images of the box and also the circuit in the following pictures.


**Images of the Assignment**:

![IMG_6444](https://github.com/NamiMod/Tangible-HCI/assets/60979433/63849656-e400-4e2e-9eee-27c8c176785f)


![IMG_6445](https://github.com/NamiMod/Tangible-HCI/assets/60979433/3a93f2f1-d150-400f-b360-b9e11d6c8b05)


![IMG_6446](https://github.com/NamiMod/Tangible-HCI/assets/60979433/d78fa914-b8ff-418f-8b14-9f876781c22a)


![IMG_6451](https://github.com/NamiMod/Tangible-HCI/assets/60979433/4896beb4-312e-46f9-9bf4-093114f94ccf)


![IMG_6447](https://github.com/NamiMod/Tangible-HCI/assets/60979433/82b0c7f4-b211-4f05-97d7-ebe8d2d84c64)


![IMG_6448](https://github.com/NamiMod/Tangible-HCI/assets/60979433/bde878c9-6b93-44ad-ac08-d3314d0300c0)


![312164541-e082888a-70b6-4b83-a8ee-8991f8e43cba](https://github.com/NamiMod/Tangible-HCI/assets/60979433/ec67168d-3ff4-47c9-8fa4-b47a16ab0005)


![Screenshot 2024-04-06 at 13 20 21](https://github.com/NamiMod/Tangible-HCI/assets/60979433/dda34971-cd59-4293-bab7-724095d3d2df)


**Video of the Assignment**:


https://github.com/NamiMod/Tangible-HCI/assets/60979433/cd1359c1-f32a-4e7a-8b16-08cbddfc37ff


**You can find the arduino code and also the python program inside the folder A3 on this repository**


**References**:


1 - Arduino Documentation - Servo ([link](https://docs.arduino.cc/learn/electronics/servo-motors/))


2 - Arduino Documentation - HC-SR04 Ultrasonic sensor ([link](https://projecthub.arduino.cc/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-7cabe1))


3 - Arduino Documentation - RGB Led ([link](https://projecthub.arduino.cc/semsemharaz/interfacing-rgb-led-with-arduino-b59902))


5 - Arduino Documentation - Blink ([link](https://docs.arduino.cc/built-in-examples/basics/Blink/))


6 - Arduino Documentation - Python and Arduino, Serial communication ([link](https://projecthub.arduino.cc/ansh2919/serial-communication-between-python-and-arduino-663756))


7 - Rohde-Schwarz - Serial Protocol ([link]([https://projecthub.arduino.cc/ansh2919/serial-communication-between-python-and-arduino-663756](https://www.rohde-schwarz.com/ca/products/test-and-measurement/essentials-test-equipment/digital-oscilloscopes/understanding-serial-protocols_254522.html#:~:text=Serial%20protocols%20are%20used%20to,components%20or%20between%20separate%20devices.&text=Serial%20protocols%20can%20be%20divided,like%20UART%2C%20I²C%20and%20SPI)))


8 - Macht, M., & Dettmer, D. (2006). Everyday mood and emotions after eating a chocolate bar or an Apple. Appetite, 46(3), 332–336. https://doi.org/10.1016/j.appet.2006.01.014 


9 - Macht, M., & Mueller, J. (2007). Immediate effects of chocolate on experimentally induced mood states. Appetite, 49(3), 667–674. https://doi.org/10.1016/j.appet.2007.05.004 


10 - Macht, M., Roth, S., & Ellgring, H. (2002). Chocolate eating in healthy men during experimentally induced sadness and joy. Appetite, 39(2), 147–158. https://doi.org/10.1006/appe.2002.0499 

