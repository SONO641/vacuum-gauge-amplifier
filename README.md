# amplifier board for thermocouple vacuum gauge

### Description of the control board for vacuum thermocouple gauge.

I found <a href="http://www.belljar.net/tcgauge.htm">
this tutorial</a>  about the operating principle of the thermocouple vacuum gauge. I designed the board below based on the article. 

A thermocouple vacuum gauge works by heating a filament at a constant current. The filament’s temperature is higher at a low vacuum because it only loses heat by radiation. The temperature is lower at higher pressure because of the heat loss via the convection of gas. A thermocouple reads the filament’s temperature and produces a DC signal at a maximum of 10mV. An instrument amplifier (INA128) is used to amplify the mV signal.

The circuit has two parts. One is to supply current to the filament. I used LM317 to limit the current to 16mA. The 5V DC supply is isolated DC. I used another DC-DC converter for the instrument amplifier to supply ±9V for INA128. Using this setup, a few mtorr pressure gives 3.7V and 100mtorr 1V. 

A commercial thermocouple gauge controller costs about $700 with a display and serial output. The amplifier board costs $25. I use ADS1115 to measure analog signals, and a Raspberry Pi to communicate.
 







