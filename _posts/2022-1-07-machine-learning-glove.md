---
layout: post
title:  "Machine Learning Glove"
date:   2021-1-07 00:00:00
categories: Personal-Project Machine-Learning Arduino
---

As a personal project to get a little look into machine learning and algorithms, I decided to create a device that would eventually be attached to a glove, recognize gestures the wearer made, and do an action based off that gesture. 
    I started off with an Arduino nano RP2040 connect that was excellent for this project. It has built in Wireless and Bluetooth capabilities, a 6-axis IMU (Inertial measurement unit) that combined an accelerometer and gyroscope, and a "Dual Core 32-bit Arm® Cortex®-M0+" that was compatible with TinyML, TensorFlow Lite, and Edge Impluse. I wired this Arduino up to a Force Sensitive Resistor (FSR) so that I could later program the device to only recognize gestures when there was a force being applied. 
    
    Nevertheless, the next step was to capture training data. I recorded a circular, shaky, and empty motion about 20-30 times each with a consistent time window for each. This consistent time window was essential to begin training a RandomForest model from the sklearn package in Python. I chose Python because it was simple and I had previous experience with the sklearn package. After training the RandomForest, I used a script I found on github to port the RandomForest Object into C++ so it could easily be used by the Arduino.

    Once I was able to recognize gestures, it was time to set up the Arduino to connect to my phone's hotspot and connect to IFTTT so I could pause and play my Spotify music with a simple gesture: circle to play, shake to stop. 

    I want to in the future take this very limited, basic project to another level by looking into using the Arduinos built in Machine Learning core with TinyML or TensorFlow Lite. I could also look more into Spotify's direct API instead of using IFTTT because I have run into long delay's using their service. This article will continue to be updated as I further develop this project


<h4>  The Device </h4>
<img src="{{'/assets/images/ArduinoDevice.JPG' | relative_url}}" />

