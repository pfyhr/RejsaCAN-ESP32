# Projects ideas and tips

I'll add fun stuff here... 


# Alarm

A beeper that only takes a few milliamperes is driven directly from one of the ESP32 pins. Alarm set on over rev in this case but can of course be oil and/or water temperatures, oil pressure (if you know the PID) or anything you want.

![IMG_20211106_095624](https://user-images.githubusercontent.com/32169384/140606426-05275d57-c2cf-4f5c-8924-d752cf405bbe.jpg)

![IMG_20211106_095633](https://user-images.githubusercontent.com/32169384/140606429-8cfcbdd0-5ed1-4404-bb08-cef960614a3e.jpg)


# CAN data on a touch screen

Just a first test of CAN info on the screen with ugly fonts ;-)  The wiring between the boards will be replaced by a super small interconnect board so the RejsaCAN is sandwich mounted behind the display board. This display board also has an SD card reader slot that you can use for logging data.

![Touch-screen(1)](https://user-images.githubusercontent.com/32169384/138956178-591b5a11-4536-44ec-ba11-c2d607cd882b.jpg)

![Touch-screen(0)](https://user-images.githubusercontent.com/32169384/138956181-5c421461-7e94-4a66-8d21-c0f54506565e.png)

# Racechrono-LIVE-telemetry-data-export
  
An example how to use the "Monitor" API in Racechrono to get a live feed of any of all data Racechrono holds using a RejsaCAN board running on car's 12V (or any board based on an ESP32 or NRF52 MCU run on 5V) to get a live feed of data from Racechrono over BLE/Bluetooth. This example code is made for a commonly available ILI9341 based display simply connected via SPI. More info and code here https://github.com/MagnusThome/Racechrono-LIVE-telemetry-data-export

https://www.youtube.com/watch?v=f61Pw1ZjPyw

![image](https://user-images.githubusercontent.com/32169384/140480398-8423526c-197f-4e5e-b384-140b0f5cd127.png)
![IMG_20211104_165820](https://user-images.githubusercontent.com/32169384/140426471-28c3b613-0b05-4048-9e02-b0b7103bf6a1.jpg)
![IMG_20211104_165918](https://user-images.githubusercontent.com/32169384/140426480-feba0d24-58bd-43de-91d2-1683e2c2daaf.jpg)


# CAN log all to Serial over USB and Bluetooth

I'm using Techstream (the software the garage uses to check up on the car) to ask for different non standard OBD2 data over the OBD2 port (steering angle, oil pressure, brake pressure...) and simultaneously log all the traffic with this RejsaCAN in the picture below, logging both the requests from Techstream and the replies from the car. Simple <a href=https://github.com/MagnusThome/RejsaCAN-ESP32/blob/main/examples/Listen%20to%20all%20CAN%20broadcasts%20(over%20Bluetooth%20and%20Serial)/getallBT.ino>Arduino code for this is in the examples directory</a>. I can either save all data over USB to my PC or save to a log file on my mobile phone over Bluetooth using for example this app https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal&hl=en&gl=US

![IMG_20211028_085844](https://user-images.githubusercontent.com/32169384/139203931-2b5d8c71-bb6d-413a-8c6a-0a8f1bfe9376.jpg)


# Using RejsaCAN as a sniffer interface with CAN software tools

I installed ESP32RET on the board and hooked it up to the CAN software tool SavvyCAN on my PC

At https://github.com/collin80/ESP32RET you get the code to put on the ESP32 so it runs as a hardware interface between the car and SavvyCAN on the PC. You can run it over USB, Bluetooth or Wifi. 

www.savvycan.com

Menu on serial port over USB to set up ESP32RET on the ESP32:

```
Config Commands (enter command=newvalue). Current values shown in parenthesis:

SYSTYPE=1 - Set board type (0 = Macchina A0, 1 = EVTV ESP32 Board
LOGLEVEL=1 - set log level (0=debug, 1=info, 2=warn, 3=error, 4=off)

CAN0EN=1 - Enable/Disable CAN0 (0 = Disable, 1 = Enable)
CAN0SPEED=500000 - Set speed of CAN0 in baud (125000, 250000, etc)
CAN0LISTENONLY=0 - Enable/Disable Listen Only Mode (0 = Dis, 1 = En)

CAN1EN=1 - Enable/Disable CAN0 (0 = Disable, 1 = Enable)
CAN1SPEED=500000 - Set speed of CAN0 in baud (125000, 250000, etc)
CAN1LISTENONLY=0 - Enable/Disable Listen Only Mode (0 = Dis, 1 = En)

CAN0SEND=ID,LEN,<BYTES SEPARATED BY COMMAS> - Ex: CAN0SEND=0x200,4,1,2,3,4
CAN1SEND=ID,LEN,<BYTES SEPARATED BY COMMAS> - Ex: CAN1SEND=0x200,4,1,2,3,4
MARK=<Description of what you are doing> - Set a mark in the log file about what you are about to do.

BINSERIAL=0 - Enable/Disable Binary Sending of CANBus Frames to Serial (0=Dis, 1=En)

BTMODE=0 - Set mode for Bluetooth (0 = Off, 1 = On)
BTNAME=ELM327-ESP32RET - Set advertised Bluetooth name

LAWICEL=1 - Set whether to accept LAWICEL commands (0 = Off, 1 = On)

WIFIMODE=2 - Set mode for WiFi (0 = Wifi Off, 1 = Connect to AP, 2 = Create AP
SSID=ESP32RETSSID - Set SSID to either connect to or create
WPA2KEY=aBigSecret - Either passphrase or actual key

```


Good videos to get started:

https://youtu.be/kdA5Gdf3FAk

https://youtu.be/GOuglqFtmOE

![image](https://user-images.githubusercontent.com/32169384/137488188-7943bd23-efe2-4454-a5ed-df7043051c72.png)

![image](https://user-images.githubusercontent.com/32169384/137488021-70c7fb58-a59d-4f41-86c1-395dd06bf2e3.png)

# Infrared camera to monitor tire temperatures on track
  
Since it runs on 12V why not make an infrared camera to measure and log your cars tire temperatures for a couple of tenners per wheel. Works with both Racechrono and Harry's Laptimer. Downloadable code and lots of info here: https://github.com/MagnusThome/RejsaRubberTrac

![image](https://user-images.githubusercontent.com/32169384/140487234-bcab10ce-9524-4d62-9b15-278a38266f7f.png)



