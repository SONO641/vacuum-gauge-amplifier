# amplifier board for thermocouple vacuum gauge

### Description of the control board for vacuum thermocouple gauge.

<img src="https://onolab-client.vercel.app/img/VacuumGaugeBoard.jpg" width="300px"/>

I found <a href="http://www.belljar.net/tcgauge.htm">
this tutorial</a>  about the operating principle of thermocouple vacuum gauges. I designed the board below based on the article. 

A thermocouple vacuum gauge works by heating a filament at a constant current. The filament’s temperature is higher at a lower pressure because it only loses heat by radiation. The temperature is lower at higher pressure because of the heat loss via the convection of gas in addition to radiation. A thermocouple reads the filament’s temperature and produces a DC signal a function of the temperature difference from the end of the wire. For the gauge I used (KJL-1518) maximum thermocouple voltage is 10mV. I used an instrument amplifier (INA128) to amplify the mV signal by a factor of 330.

The circuit has two parts. One is to supply current to the filament. I used LM317 to limit the current to 16mA. The 5V DC supply for the filament has to be isolated, otherwise thermocouple won't work. I used another DC-DC converter for the instrument amplifier to supply ±9V for INA128. Using this setup, a few mtorr pressure gives 3.7V and 100mtorr 1V between SIG and REF pins. Calibrate the gauve following the artible above.  

A commercial thermocouple gauge controller costs about USD 700 with a display and serial output. Parts for the amplifier board was about USD 25. I use ADS1115 to measure analog signals, and a Raspberry Pi to communicate and log the pressure to a server. Total cost was under USD 100. 

Connect filament +/- to gauge pins 1 and 7, and TC gauge +/- to pin 5/3 of the thermocouple gauge. Apply 5V DC voltage between VIN and GND. Measure voltage between SIG and REF. Applying 5V to enable (EN) to apply current to the filament; pulling EN pin down will shut off the filament current. It may take a few min to filament to heat up, and give steady vacuum readings.    
 







