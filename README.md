# amplifier board for thermocouple vacuum gauge

### instructions for building a power supply and readout for vacuum thermocouple gauge.

I found <a href="http://www.belljar.net/tcgauge.htm">
this tutorial</a> about the operating principle of the thermocouple vacuum gauge. I wanted to make a board using a modern instrument amplifier. The output ranges from 0 to 3.7V; high voltage corresponds to low vacuum (a few mmHg). I use ADS1115 to measure analogue signal. 

A commercial thermocouple gauge controller currently costs about $700 with a display and serial output. The amplifier board costs $25 to make. 

A thermocouple vacuum gauge works by heating a filament at constant current (16mA). The temperature of the filament is higher at low vacuum because it only radiates heat but at higher pressure heat can be lost by convecting gas. A thermocouple reads the temperautre of the filament, and produce a DC signal up to 10mV. An instrument amplifier (INA128) is used to amplify the signal by 334 times by using 150 ohm registor. 

The circuit has two parts. One is to supply current to filament. I used LM317 to limit current to 16mA. The 5V DC supply is isolated DC by PEP1-S5-S5-M. I used another DC-DC converter to use ±9V (PEP1-S5-D9) for the instrument amplifier. 

Using this set up, a few mtorr produced 3.7V and 100mtorr produced 1V. 






