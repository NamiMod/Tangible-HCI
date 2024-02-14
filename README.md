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




**Image of the Assignment**:


![IMG_4973](https://github.com/NamiMod/Tangible-HCI/assets/60979433/47d8cbc1-ea51-45ba-a8a8-5fc646430023)


![IMG_4972](https://github.com/NamiMod/Tangible-HCI/assets/60979433/2e02c0ba-ed4c-4162-a7ca-bc9e364cbd77)


![IMG_4971](https://github.com/NamiMod/Tangible-HCI/assets/60979433/bbe0e640-8260-4556-91e2-414460215c62)


![IMG_4970](https://github.com/NamiMod/Tangible-HCI/assets/60979433/69e02711-fe62-407e-86a7-205dc4a9c3f5)


**Video of the Assignment**:


**You can find the arduino code insilde the folder A1 on this repository**


**References**:


1 - Arduino Documentation - Servo ([link](https://docs.arduino.cc/learn/electronics/servo-motors/))


2 - Arduino Documentation - Touch Sensor ([link](https://projecthub.arduino.cc/hibit/using-touch-sensor-with-arduino-83b957))


3 - Arduino Documentation - DHT11, Humidity Sensor ([link](https://projecthub.arduino.cc/arcaegecengiz/using-dht11-12f621))


4 - Arduino Documentation - Serial Communications with Python Program ([link](https://projecthub.arduino.cc/ansh2919/serial-communication-between-python-and-arduino-663756))


5 - Stackoverflow - Generate a tone in python ([link](https://stackoverflow.com/questions/56592522/python-simple-audio-tone-generator))
