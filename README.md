# DMB-100
Digital Marine Balances - 100 (max. weight = 100g)

! ! ! ! !
Before PCB mounting:
R43, R44, C24 - do not install (by default). Install if you want to use B channel of ADC HX711.
R25, R33 - do not install if you use internal on-chip oscillator (by default).
R29, R39 - do not install, data rate control, installed R31, R40 means 0: 10Hz (by default); installed R29, R39 means 1: 80Hz.
R20, R23 - do not install if you use internal pull-up's for EPS32 GPIO2 and GPIO4

Something about RTC. You can use many different RTC's in SOIC-8 case and pin-to-pin compatible (if you need time and date on the display). I tried 2 types, one with two domains of power supply (battery and Vcc) and one only with Vcc (it is much cheaper). So, if you use second type with one domain, for example PCF8563, please do steps:
R1 - install 0 Ohm resistor if you use external power supply for RTC (after turning off the device real clock timer progress will be lost). I use this option for first tests. In this case, R2 - do not install.
R2 - install 0 Ohm resistor if you use 2032 battery for RTC (after turning off the device real clock timer progress will be saved). In this case, R1 - do not install.
R5 - not install. This resistor needs to be installed if you use RTC like M41T81

Shortly:

If you use RTC with two power supply domains, like M41T81:
R5, R1 - install 0 Ohm resistors, R2 - do not install

If you use RTC with one power supply domain, like PCF8563:
R2 - install 0 Ohm resistors, R5, R1 - do not install
