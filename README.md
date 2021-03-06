# CoralDefense-Webapp
Web application version of CoralDefense. Sends and receives data from Arduino via the internet. Uses SQL, php, and Arduino languages.

## To Launch
-----------
* Add files to the public_html folder on the webserver.
* Have the project code running on an Arduino.
## To Upload Code to ESP Module
----------- 
* The ESP Module needs to be programmed seperately from the Arduino board with it's own arduino code. In order to do this use a programmer such as this one https://www.amazon.com/ESP-01S-Programmer-ESP8266-Wireless-4-5-5-5V/dp/B07V54DWXH/ref=sr_1_3?crid=100XNOBF8185B&dchild=1&keywords=usb+to+esp8266+serial+wireless+wifi+module+adapter+board&qid=1613601736&sprefix=serial+to+usb+adapter+esp%2Caps%2C157&sr=8-3 
* The programmer has two modes prog and uart to upload your code use prog
### index.php
------------
* Contains the HTML and CSS for the site.
* uses embedded javascript to allow for dynamic buttons and sensor monitor
### ESPtable1.sql
----------------
* Initializes sql table.

### get_data.php
---------------
* gets newest data from livetable. redraws sensor monitor with new values, called by js embedded in index

### send_arduino_data.php
------------------------
* Sends data to Arduino. writes to the command file that arduino gets

### recieve_arduino_data.php
---------------------------
* Recieves sensor data from the arduino and sends to sensor tables. 

### Sensor monitor
---------------------------
![alt text](/pictures/sensormonitor.gif?raw=true)
* Linked using embedded JavaScript that uses AjAx's load function on a timer to run the "get_data.php" script

### Command row
---------------------------
![alt text](/pictures/commandrow.gif?raw=true)
* Each button has a invisible linked button, when the user clicks the visible on button a js script runs that calls send_arduino_data.php
* The invisible buttons are used because when it was visible the buttons would deform and rather than fix this it was easier to run the js on invisible objects.

### Sources and Important docs
---------------------------
* Google drive with important presentations:https://drive.google.com/drive/folders/1LOZ6MqgfZt55XDYMcP-2p3SdXCsBt3-Y?usp=sharing
* Installing ESP8266 library to arduino ide:https://arduino-esp8266.readthedocs.io/en/latest/installing.html 
* Arduino HTTP Requests:https://arduinogetstarted.com/tutorials/arduino-http-request
* ESP8266 WiFi library examples:https://github.com/esp8266/Arduino/tree/master/libraries/ESP8266WiFi/examples
* AjaX load documentation:https://api.jquery.com/load/ 
* JQuery ready used to make sure page loads before running javascript:https://learn.jquery.com/using-jquery-core/document-ready/ 
* Setinterval, used by sensor monitor:https://www.w3schools.com/jsref/met_win_setinterval.asp
* JS onclick used by command buttons:https://www.w3schools.com/jsref/event_onclick.asp 
* VsCode Arduino extension:https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.vscode-arduino
* Comm architecture:
![alt text](/pictures/commarchitecture.png?raw=true)
