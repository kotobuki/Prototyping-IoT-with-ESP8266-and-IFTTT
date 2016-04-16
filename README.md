# Prototyping IoT with ESP8266 and IFTTT

## Setting up Your ESP8266 Board

1. Solder headers to your board
2. Turn on the power slide switch
3. Connect a USB (A to Micro B) cable

## Setting up an Environment for ESP8266

1. Install Arduino 1.6.8 from the Arduino website.
2. Start Arduino and open Preferences window (**File** > **Preferences** on Windows, **Arduino** > **Preferences...** on Mac OS X).
3. Enter http://arduino.esp8266.com/stable/package_esp8266com_index.json into **Additional Board Manager URLs** field.
4. Hit OK. Then navigate to the Board Manager by going to **Tools** > **Boards** > **Boards Manager**. Look for esp8266. Click on that entry, then select Install.
5. With the Board addon installed, all that’s left to do is select “SparkFun ESP8266 Thing Dev” from **the Tools** > **Boards** menu.
6. Then select your serial port number under the **Tools** > **Port** menu.
7. Navigate **File** > **Examples** > **ESP8266** (as a part of Examples from Custom Libraries) > **Blink**
8. Hit the Upload button on your Arduino IDE to start uploading
9. If you see the onboard LED is blinking, that means you finished setting up successfully
10. Navigate to **Library Manager** by going **Sketch** > **Include Library** > **Manage Libraries...**
11. Look for PubSubClient and install
12. Look for ArduinoJson and install
14. Open a **Serial Monitor** by going **Tools** > **Serial Monitor**
15. Change the baud rate from 9600 bps (default) to 115200 bps

## How ESP8266 Different from Arduino Uno

* A Wi-Fi (802.11 b/g/n) wireless modem is integrated
* The processor is faster and has much memory space
3.3V, instead of 5V
* Limited number of pins
* Some pins (i.e. D0) are used for special functions
* The on-board LED is connected to D5, instead of D13
* Only one analog input (i.e. A0) and range is 0 - 1V, instead of 0 - 5V

## IFTTT Primer

1. Point your web browser to https://ifttt.com/ and create an account
2. Install an application for your smart phone (if available)
3. Create a recipe to get familiar with IFTTT terms (e.g. recipes, channels, triggers, actions and so on)

## Example of ESP8266 as a Trigger Device

1. Point your web browser to https://ifttt.com/maker to connect the Maker channel to your account
2. Copy your key and paste it to your notebook
3. Create a recipe; choose the Maker channel for the trigger and choose something (e.g. IF Notifications) for the action
4. Connect a button and a resistor to the D4 pin of your board
Open IFTTT_Trigger
5. Navigate to a tab named 'config.h' and replace the SSID, password and key with your's
6. Upload the example to the board, hit the button and see what happens

## Example of ESP8266 as an Action Device

1. Point your web browser to https://beebotte.com/ and create an account
2. Create a Channel (e.g. ifttt) and a Resource (e.g. action)
3. Copy the Channel Token and paste it to your notebook
4. Create a recipe; choose something (e.g. Instagram) as the trigger and choose the Maker channel for the action URL: https://api.beebotte.com/v1/data/write/ifttt/action?token=**********
5. Open IFTTT_Action_Beebotte
6. Navigate to a tab named 'config.h' and replace the SSID, password and key
7. Upload the example to the board
8. Provoke the trigger and see what happens

## Let’s Try!

* Create an example to fire a trigger when your indoor brightness changes (e.g. from bright to dark); How might we convert the voltage range from 0 - 3.3V to 0 - 1V, to fit the range of the analog input pin of your board?
* Write a code to move a servo motor when something happened (e.g. a person posted a Tweet); How might we connect a servo motor to your board and control it?

## Resources

* [ESP8266 Thing Development Board Hookup Guide]( https://learn.sparkfun.com/tutorials/esp8266-thing-development-board-hookup-guide)
* [MQTT (MQ Telemetry Transport)]( http://mqtt.org/)
* [Arduino Client for MQTT]( http://pubsubclient.knolleary.net/)

## Related Toolkits

* [Blynk]( http://www.blynk.cc/)
* [Node-RED]( http://nodered.org/)