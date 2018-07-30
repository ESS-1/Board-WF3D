# Board-WF3D
## Pin Functions

|No.   |Type  |Name |Description                                                                                        |
|------|------|-----|---------------------------------------------------------------------------------------------------|
|1,2   |PWR   |Vin  |Supply voltage input; 5V/12V/24V nom. (4V to 30V).                                                 |
|3,4,5 |PWR   |GND  |Ground.                                                                                            |
|6     |PWR   |Vio  |UART IO voltage input; 5V nom. (4.5V to 5.5V).                                                     |
|7     |PWR   |Vcco |3.2V output; up to 200 mA.                                                                         |
|8     |OUT   |#SRST|Software controlled reset output; open collector; up to 15V, 15 mA nom. (Absolute maximum: 100 mA).|
|9     |IN    |#RST |Reset input; active low. If external voltage is applied, it should not exceed Vcco.                |
|10    |IN/OUT|#SOE |Pulling down this pin through 4.7K enables UART diagnostic output during boot. During normal operation this pin is an output; low level indicates that UART is active. Driven from Vcco.|
|11    |-     |NC   |Do not connect this pin.                                                                           |
|12    |IN    |RX   |UART RX input.                                                                                     |
|13    |IN/OUT|BOOT |If driven low at startup, the module is switched to the programming mode. If configured in software, driving this pin low for 5 seconds when the module is running causes settings reset. When configured as output, logic 0 voltage is Vcco/2; output resistance >2 kOhm.|
|14    |OUT   |TX   |UART TX output.                                                                                    |
