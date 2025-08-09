# ***--------slot-pilot-controller/README.md***



\# Slot Pilot Controller (Raspberry Pi Pico 2 W)



Arduino firmware for the handheld \*\*controller\*\*:

\- \*\*Web OTA\*\* at `/update` (HTTPUpdateServer)

\- \*\*Arduino IDE OTA\*\* (Network Port) with hostname \*\*slot-pilot\*\*

\- \*\*/debug\*\* page for viewing logs, toggling debug, setting level, and controlling the car’s debug

\- OLED UI with menus, EEPROM profile storage, UDP link to the car



\## Internal Electronics — Parts List (controller only)



\- \*\*Raspberry Pi Pico 2 W\*\* (RP2350, Wi-Fi)

\- \*\*OLED 0.96" 128×64 I²C\*\* display (SSD1306, 3.3 V)

\- \*\*2-axis thumb joystick\*\* with center push (10 kΩ pots)

\- \*\*0.1 µF (100 nF) ceramic capacitors\*\* for local decoupling (near MCU/display/joystick board) — Qty 4–6

\- \*\*1000 µF electrolytic capacitor\*\* (16–25 V) for bulk input smoothing — Qty 1

\- \*\*4.7 kΩ or 10 kΩ resistors\*\* (I²C pull-ups if your OLED board does not already include them) — Qty 2

\- \*(Optional)\* 1× tactile button if you want a separate menu button from the joystick press



> Only internal electronics are listed (no screws, inserts, etc.).



\## Pins (defaults in this firmware)



\- I²C OLED: \*\*SDA=GPIO4\*\*, \*\*SCL=GPIO5\*\* (I²C0), VCC=3.3 V  

\- Joystick: X → \*\*ADC0 (GPIO26)\*\*, Y → \*\*ADC1 (GPIO27)\*\*, Press → \*\*GPIO6\*\* (INPUT\_PULLUP)



\## Build (Arduino IDE)



\- \*\*Core:\*\* \*Arduino-Pico (RP2040/RP2350) by Earle Philhower\*

\- \*\*Board:\*\* \*Raspberry Pi Pico 2 W\*

\- \*\*Tools → Flash Size:\*\* select a partition \*\*with LittleFS\*\* (needed for web OTA page)

\- \*\*Libraries:\*\* `Adafruit\_GFX`, `Adafruit\_SSD1306` (others are built-in)



\## Network



\- Controller \*\*joins the car AP\*\* (STA): `SlotPilot\_CAR\_OTA / update123`

\- \*\*Web OTA:\*\* `http://<pico-ip>/update`

\- \*\*IDE OTA:\*\* Network Port \*\*slot-pilot\*\*

\- \*\*Debug:\*\* `http://<pico-ip>/debug`



