# LoRaWAN Application on SAMR34 to track location using GPS module 
This application demonstrates the Location Tracking Application using SAMR34 and GPS module. User will be able to send GPS coordinates to Network Server and Cayenne Application Server.
This application has been tested on following boards:
[ATSAMR34-XPRO](https://www.microchip.com/DevelopmentTools/ProductDetails/dm320111 "ATSAMR34-XPRO")+[mikroBUS Xplained Pro](https://www.microchip.com/Developmenttools/ProductDetails/ATMBUSADAPTER-XPRO "mikroBUS Xplained Pro")+ [GPS click](https://www.mikroe.com/gps-click "GPS click")
![](https://i.imgur.com/HM7QZ22.jpg)

### Features

- Helps monitor location of an asset
- Enables user for Long Range Wireless Communication
- Secure communication with Network Server and Application Server
- Use of Cayenne Application Server enables tracking information on a Phone App
- Data logging available on Cayenne Application Server

### Setup
![](https://i.imgur.com/JWV0FNL.jpg)

This application requires user to have the following setup
- Internet
- Gateway
- Network Server ([The Things Network](https://www.thethingsnetwork.org/ "The Things Network"))
- Application Server([Cayenne Mydevices](https://mydevices.com/cayenne/signin/ "Cayenne Mydevices"))
- ATSAMR34-XPRO
- mikroBUS Xplained Pro on EXT1 
- GPS click mounted on the mikroBUS Xplained Pro
- Micro USB
- PC
Connect the EDBG USB port of ATSAMR34-XPRO to PC using the micro usb and program the Application using [Atmel Studio 7](https://www.microchip.com/mplab/avr-support/atmel-studio-7 "Atmel Studio 7")

### Implementation Details
This application of SAMR34 configures the GPS module (UBLOX LEA-6S) to send GPS coordinates every 10 seconds. The GPS coordinates are received by SAMR34 in [NMEA protocol](https://en.wikipedia.org/wiki/NMEA_0183 "NMEA protocol"). As this application demonstrates Location Tracking. User will be able to send the GPS coordinates of the board every 10 secs(configurable) after a join to network server.
“Green LED Blink” on ATSAMR34-XPRO denotes GPS coordinates transmission
“RED LED Blink” on GPS Click board denotes “Fix” – Acquiring a lock onto 3 or more satellites to calculate the GPS coordinates
User can OTAA/ ABP join procedure. By default the demo is configured to communicate on NA915 Band. User can modify this Application to work for other regions like EU868, AU915, THAI923, JPN923, KR920, IND865 etc., To configure the demo parameters user needs to modify config_app.h
For ease of debugging logs can be displayed. While connected to the PC using EDBG USB use a terminal emulator like TeraTerm. Find the com port on Terminal Emulator and use the following serial settings 9600 bps, 8 bits, no parity, 1 Stop bit, no flow control. After a successful programming and join to network, each reset on board or a power cycle, the application will restore its configuration due to the presence of a persistent data storage (PDS) unit active. After a reset/power cycle of board if the user wants to rejoin the network to avoid using PDS configuration user can enter any key on TeraTerm to rejoin the network and continue the demo.

**Note:** This Application example does not utilize the Assisted GPS features which enable better computation of GPS coordinates in indoor environments.
The demo Application is not optimized for power consumption. 

### Cayenne Application Server extracting GPS Application data from The Things Network

## Live Data
![](https://i.imgur.com/Gzxwscq.jpg)

## GPS Location
![](https://i.imgur.com/RtOreXK.jpg)


### Compilation Info
This software was written for the GNU GCC and IAR for ARM. Other compilers may or may not work.
###Contact Information
For further information, visit http://www.microchip.com.

### References
[Connecting Network Server(The Things Network) to Application Server (Cayenne) ](https://www.thethingsnetwork.org/docs/applications/cayenne/ "Connecting Network Server(The Things Network) to Application Server (Cayenne) ")
