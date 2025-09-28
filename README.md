# MCLogger
MCLogger - Neural Wood - Institute of Computational Design and Computing for Architecture - University of Stuttgart

## Description
This repository contains the codes and procedures to utilize the MCLogger tool for measuring and storing data: Wood Moisture content, ambient temperature and humidity, time, board, and section numbers. This data is obtained through a series of sensors connected to a Raspberry pi. The Hardware includes: a timber moisture content sensor, an ambient temperature and humidity sensor (DTH 22), a 16x2 LCD display, a Raspberry Pi camera module 3, and 4 input buttons, all connected to a Raspberry Pi 4 and supported by a 3D printed case.  


## Documents
Documentation of the project is organized in 3 main folders. 
- 3D models of the case: contains design files and final design. 
- Codes
- Codes for training MV model.

## Using the tool
1. Connect the external power bank to the Raspberry Pi.
2. After a few seconds, the `MCLogger.py` will be executed automatically.
3. Insert the Wood MC sensor inside the case, turn it on, and calibrate it by pressing the arrow button (point the tool high and far away from any surface).
4. Once both elements are up and running, the display will show the current ambient temperature and humidity, the last moisture content predicted by the camera, and the number of board and section in format "board/section".
5. Using the 4 buttons in the front of the MCLogger from left to right:
    - Button 1: Accept and store data.
    - Button 2: Create a new prediction.
    - Button 3: No use in the main screen but used to go back when selecting a board and section number.
    - Button 4: Enter the menu to change the board and section, and once inside this menu, move the numbers up.
6. Select the desired number of boards by pressing the Button 4. Move up and down with Button 3 and Button 4 until you find the number of the board. To accept, press button 1. Then select the section following using the same buttons to move up and down and accept the change.
7. Back in the main screen, use Button 2 to generate a new prediction. If the prediction matches the number on the screen of the Wood MC sensor, then the value can be stored by pressing button 1. 
**IMPORTANT:** There is a 1-second delay between the prediction and the storing of the value. Verify that the number was stored when the "STORE" text appears on the display. The section of the board will automatically increase by 1.
8. The MCLogger tool has a width of exactly 10 cm that can be used as a module to move between one section and another of the board.
9. Data stored will be sorted in 3 places:
    - JSON file: Data will be saved in a JSON file called `MCLogger_inputs.json`. Here you can find all the values of date, time, name of board, section, ambient humidity and temperature, and wood moisture content.
    - Images in folder: Images taken by the camera will be reduced in size and stored for verification purposes in the folder `Stored_img` divided by board and named with the number predicted by the model.
    - CSV files: Additionally, the labels predicted and accepted by the user will be used together with the image to enlarge the dataset to increase the robustness of the model.

## Tutorial
- Hardware assembly and connections.
- Creating a virtual environment.
- Training machine vision model.
