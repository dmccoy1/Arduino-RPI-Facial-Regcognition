## Smart Door Lock with Facial Recognition

###  Project Overview

For this project, I built a **smart door lock system** that uses **facial recognition** to identify authorized users and control a physical lock.
This is a great example of how **artificial intelligence, computer vision, and physical computing** can work together in a real-world application.

* **Raspberry Pi** performs **facial recognition** with **OpenCV** and **face_recognition**.
* The **Arduino** controls a **servo lock** and **LED indicators**, and signals its state with a buzzer.
* The two communicate over **serial** — when a recognized face is detected, the Raspberry Pi signals the Arduino to unlock the door.

---

### How It Works

* The camera feed from **Raspberry Pi** is processed in real-time.
* If a recognized face is found, the Raspberry Pi emits a “pass” command over Serial.
* The Arduino then:

  * Turns its **LED green**
  * Activates its **servo** to unlock the lock
  * Plays a short **positive chime with its buzzer**

If a face is not recognized, the Raspberry Pi signals “fail”, causing the Arduino to:

* Turn its **LED red**
* Keep its **servo locked**
* Play a **negative chime** with its buzzer.

---

###  Raspberry Pi — Face Recognition

To set up face recognition with your Raspberry Pi, follow this guide from Core Electronics:

➡ [Face Recognition with Raspberry Pi and OpenCV](https://core-electronics.com.au/guides/raspberry-pi/face-recognition-with-raspberry-pi-and-opencv/)

This guide covers:

* Installing `OpenCV` and `face_recognition`.
* Setting up your camera.
* Training the AI tool to detect and recognize faces in real time.

Save your trained face encodings in `encodings.pickle`.

---
 
###  Arduino — Hardware Control

####  Hardware Connection:

| Component | Pin |
|---------|---------|
| RGB LED (Red) |  3 |
| RGB LED (Green) |  5 |
| RGB LED (Blue) |  6 |
| Buzzer |  7 |
| Servo |  2 |


![Door Unlock System (1)](https://github.com/user-attachments/assets/9962f0a1-3c32-438b-98eb-cc07e8aa9bed)

