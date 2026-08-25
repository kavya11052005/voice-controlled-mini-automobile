# Voice Controlled Mini Automobile

An embedded robotics platform built with an Arduino UNO microcontroller. The system features real-time voice-command navigation, Bluetooth remote driving, and autonomous obstacle avoidance capabilities.

## Features
* **Voice Command Navigation:** Accepts 5 real-time voice inputs (Forward, Backward, Left, Right, Stop) via smartphone Bluetooth transmission.
* **Autonomous Collision Avoidance:** Uses an ultrasonic sensor mounted on a 180° servo motor to actively scan and navigate clear paths when obstacles are detected.
* **Bluetooth Remote Control:** Supports manual directional driving inputs via serial communication over UART.

## Hardware Components
* **Microcontroller:** Arduino UNO (ATmega328P)
* **Wireless Module:** HC-05 Bluetooth Module
* **Distance Sensor:** HC-SR04 Ultrasonic Sensor
* **Actuators:** SG90 Servo Motor, 4x DC Motors
* **Motor Driver:** L298N Dual H-Bridge Driver

## Tech Stack
* **Language:** C / C++
* **Environment:** Arduino IDE
* **Protocols:** UART Serial Communication, PWM Control

## System Logic Flow
1. **Startup:** Initializes serial communication at 9600 baud and centers the radar servo to 90°.
2. **Manual / Voice Mode:** Decodes incoming serial characters (`F`, `B`, `L`, `R`, `S`) to update motor direction.
3. **Autonomous Mode (`A`):** 
   - Continuously measures forward distance.
   - If distance < 15cm, halts vehicle and scans left (150°) and right (30°).
   - Steers toward the direction with the largest clear path.

## Setup & Installation
1. Open `voice-controlled-mini-automobile.ino` in the Arduino IDE.
2. Select **Arduino Uno** under **Tools -> Board**.
3. Connect your board via USB and select the correct **Port**.
4. Compile and upload the sketch to the board.<img width="516" height="713" alt="Screenshot 2026-08-25 170835" src="https://github.com/user-attachments/assets/e7d36837-f20e-4f39-8af9-b3cae08993d5" />
<img width="498" height="699" alt="Screenshot 2026-08-25 170826" src="https://github.com/user-attachments/assets/9786f563-47b2-463f-adb4-e8ce2a5d8a4c" />
<img width="502" height="702" alt="Screenshot 2026-08-25 170815" src="https://github.com/user-attachments/assets/bcaba0b3-6aab-4aaa-8fa9-52e1a6be34e9" />
<img width="505" height="711" alt="Screenshot 2026-08-25 170733" src="https://github.com/user-attachments/assets/b79d8401-3000-4d5c-be86-4682f075877a" />
<img width="506" height="715" alt="Screenshot 2026-08-25 170719" src="https://github.com/user-attachments/assets/0cf82a12-3ebb-493a-b3c8-25dfd2b99060" />
