# AT
Projects regarding Android Things course.

Solo project : 
Smile detector : using Haar Cascades and a Raspberry Pi.

# Android Things Project
Solo project by Moldovan Daniela-Mihaela

Smile Detector: 
Using a camera the program will detect whether the person is smiling. In a positive case (person is smiling) it will take a picture. 

## A demo can be found in the *video* folder.

## Schematics 
![Image of schematics](https://github.com/at-cs-ubbcluj-ro/solo-project-mikellah/blob/master/html/images/camera.png)

## Pre-requisites
For this project I have used : 
* Raspberry Pi 3 model B+
* USB camera

## Setup and Build 
First we take our RPi and enable the camera in the configurations.This can either be done by using *sudo raspi-config* or enabling it in *Preferences*.

Once we have OpenCV installed and the camera working we can run the source code.
The following is the code provided in the Python file found in the *smile_detection* folder:
![Image of code](https://github.com/at-cs-ubbcluj-ro/solo-project-mikellah/blob/master/html/images/code.jpg)

First we import the .XML files ; the cascades which will detect the structures of the face : frontal view of the face, eyes and the smile.

Next we make a function that will take each frame and turn it grayscale, then it goes through the process of detecting how many eyes there are in each frame and how many smiles.

To help with this I had the number of eyes and smiles detected printed in the terminal.The lines that are commented are actually there to form rectangles that help with the position of what we are detecting. 

Since we are taking a picture of what is displayed, I decided to comment said rectangles but I have used them for testing.
For each frame we have a list of eyes and smiles so I have used said list's size in such way that if it detects at least 2 'eyes' and 1 'smile' in the frame it will take a picture. 
I took into account the fact that for a 'selfie' we are supposed to have our eyes open and to be smiling.The *while* is there to loop the entire function. 

We can end the session by pressing either the 'Esc' button or 'q' on our keyboards.

### Running 
You can run the program by opening a *Terminal* on your Raspberry Pi, changing to the directory where the Python file is located and executing the program by writing `python smile_detection.py` to run it.

