# WF3D Board
## Pin Functions

|No.   |Type  |Name |Description                                                                                        |
|------|------|-----|---------------------------------------------------------------------------------------------------|
|1,2   |PWR   |Vin  |Supply voltage input; 5V/12V/24V nom. (4V to 30V).                                                 |
|3,4,5 |PWR   |GND  |Ground.                                                                                            |
|6     |PWR   |Vio  |UART IO voltage input; 5V nom. (4.5V to 5.5V).                                                     |
|7     |PWR   |Vcco |3.2V output; up to 200 mA.                                                                         |
|8     |OUT   |#SRST|Software controlled reset output; open collector; up to 15V, 15 mA nom. (Absolute maximum: 100 mA).|
|9     |IN    |#RST |Reset input; active low. If external voltage is applied, it should not exceed Vcco.                |
|10    |IN/OUT|#SOE |Pulling down this pin through 4.7K enables UART diagnostic output during boot. During normal operation, this pin is an output; low level indicates that UART is active. Driven from Vcco.|
|11    |-     |NC   |Do not connect this pin.                                                                           |
|12    |IN    |RX   |UART RX input.                                                                                     |
|13    |IN/OUT|BOOT |If driven low at startup, the module is switched to the programming mode. If configured in software, driving this pin low for 10 seconds when the module is running causes settings reset. When configured as output, logic 0 voltage is Vcco/2; output resistance >2 kOhm.|
|14    |OUT   |TX   |UART TX output.                                                                                    |

## Display Interface
The current version of firmware supports an SSD1306-based 128x64 OLED in I2C configuration connected as follows:
3.2V - J2.1
SCL  - J2.2 (GPIO14)
SDA  - J2.3 (GPIO5)
GND  - J2.5

Display should have its own pull-up resistors on I2C bus, because these resistors are missing from the rev. 1.1 board.
Widely available Chinese displays have a pair of 10K pull-ups and practically work without modifications, but the integrity of I2C signals with 10K resistors is far from perfect.
It is recommended to replace both resistors by 3K3.
If there is a 3.3V LDO on the display board, it is preferred to replace it by a jumper to avoid extra voltage drop.
Total current consumption of external devices connected to the 3.2V rail should not exceed 200mA.
