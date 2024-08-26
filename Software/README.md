# Meadowlark-Mini Software

![Banner showing PCB](https://github.com/colinhalebrown/Meadowlark-Mini/blob/main/Documentation/images/banner.jpg)

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
