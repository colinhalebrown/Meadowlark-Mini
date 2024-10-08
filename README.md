# Meadowlark-Mini

Dual deploy programable flight computer for amature rocketry. Equipt with a beeper, physical interrupt, battery charger/monitoring, ignighter indicators, logging to MicroSD, IMU, and Pressure sensor. The goal is to offer a feature rich contnroller that can fit inside a 29mm chassis with the creature comforts of modern controllers. The system is powered by a onboard RP2040 microcontroller. Running at 125MHz with dual core operation for data collection and flight tracking.  

![Banner showing PCB](https://github.com/colinhalebrown/Meadowlark-Mini/blob/main/Documentation/images/banner.jpg)

### Hardware Specs
* 260 to 1260 hPa absolute pressure range
* 0.5 hPa absolute pressure accuracy
* +/- 0.025 hPa relative pressure accuracy
* +/- 16g accelerometer range
* +/- 2000 dps gyroscope
* embedded temperature compensation
* 20,000g shock rated
* ~130mA operating consumption 
* Buzzer 80db
* MicroSD data storage

### Hardware Improvements
* add RESET pads for debugging
* move BOOT pads closer together
* Choose different SDcard pins to enable writing code with the picoSDK

### Testing
- [x] Hardware validation
- [x] Firmware Initialized
- [ ] Test Functionallity
        - [x] Indicator light
        - [x] Pyro circuit
        - [x] buzzer
        - [ ] SDcard
        - [ ] Pressure Sensor
        - [ ] IMU
- [ ] Software endurance test
- [ ] Simulated flight test
- [ ] Passeenger flight tests (collect data and tune triggers)
- [ ] Flight as main controller
- [ ] Flight as secondary controller

Repeat any tests until the controller passes with reliable behavior.

# Hardware
![PCB size](https://github.com/colinhalebrown/Meadowlark-Mini/blob/main/Documentation/images/IMG_4509.jpeg)

When designing the board I wanted to a microSD card slot that locks the card into the board. After our push card lock slot ejected the SD card in flight at spaceport I wanted to have a more robust card holder. 

![PCB MicroSD card Example](https://github.com/colinhalebrown/Meadowlark-Mini/blob/main/Documentation/images/IMG_4576.jpeg)

The other china specific part that was hard to find was a small buzzer. Getting the board to fit in a 29mm body tube meant I needed to shrink my components as much as possible.

### [Hardware Details](https://github.com/colinhalebrown/Meadowlark-Mini/tree/main/Hardware)

# Software
I started by testing functionality of the controller with the arduino IDE. That worked well however I wanted to shift to using the PICO-SDK with vscode to write softwar with the goal of making the firmware more reliable and more power efficent.

### Pinout
|System         |Signal Type   |Label| GPIO |Verified|
|---------------|--------------|-----|------|--------|
|Indicator LED  |Digital Output|D13  |GPIO13|Y       |
|Buzzer         |Digital Output|A0   |GPIO26|Y       |
|Battery Monior |Analog Input  |A1   |AD1   |Y       |
|Pyro 1         |Digital Output|D12  |GPIO12|Y       |
|Pyro 2         |Digital Output|D4   |GPIO6 |Y       |
|Pressure Sensor|I2C           |SDA, SCL|GPIO2, GPIO3|   |
|IMU            |I2C           |SDA, SCL  |GPIO2, GPIO3| |
|MicroSD Card   |SPI           |MISO, MOSI, SCK, D10|GPIO20, GPIO19, GPIO18, GPIO10|Y|

# Status
Currently the system needs more programming and testing. I fried controllers I/O while working with the board so a new RP2040 will need to be soldiered to the board. 

I plan to repair the test article and finish the functionality tests with the existing design using the arduino IDE. I need to update the PCB to develop code using vscode in the future.
