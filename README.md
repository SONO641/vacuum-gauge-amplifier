# amplifier board for thermocouple vacuum gauge

### Description of the control board for vacuum thermocouple gauge.

I found <a href="http://www.belljar.net/tcgauge.htm">
this tutorial</a>  about the operating principle of the thermocouple vacuum gauge. I designed the board below based on the article. 

A thermocouple vacuum gauge works by heating a filament at a constant current. The filament’s temperature is higher at a lower pressure because it only loses heat by radiation. The temperature is lower at higher pressure because of the heat loss via the convection of gas in addition to radiation. A thermocouple reads the filament’s temperature and produces a DC signal. The voltage is a function of temperature difference from the end of the wire (cold junction). For the gauge I used (KJL-1518) maximum voltage is 10mV. An instrument amplifier (INA128) is used to amplify the mV signal.

The circuit has two parts. One is to supply current to the filament. I used LM317 to limit the current to 16mA. The 5V DC supply is isolated, otherwise thermocouple won't work. I used another DC-DC converter for the instrument amplifier to supply ±9V for INA128. Using this setup, a few mtorr pressure gives 3.7V and 100mtorr 1V. 

A commercial thermocouple gauge controller costs about $700 with a display and serial output. The amplifier board costs $25. I use ADS1115 to measure analog signals, and a Raspberry Pi to communicate. 

Connect filament +/- to gauge pins 1 and 7, and TC gauge +/- to pin 5/3 of the thermocouple gauge. Apply 5V DC voltage between VIN and GND. Measure voltage between SIG and REF. Applying 5V to enable (EN) to apply current to the filament; pulling down shuts off the filament current. It may take a few min to filament to heat up, and give steady readings.    
 







