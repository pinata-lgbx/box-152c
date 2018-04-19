# Pinata

## Hardware specifications.

### Lights:
- 3x lights with different power and spectre, one for growing, one for early flowerng and one for late flowering.
- 3x 220v relays for light activation (3x DO needed).
- 3x light detector sensors as light activation feedback (3x DI needed).
- total gpio: 3 DO and 3 DI channels.

### Ventilation:
- main outflow vent with 2-speed day/night operation modes (2400/2200 rpm and 180/150 m3/h). 
- 1x 220v relay for main vent speed selection (1x DO needed).
- 1x upper inflow cooling fan with PWM speed control for growing cabinet (1x PWM DO needed). (size to be determined)
- 2x lower inflow cooling fans with PWM speed control for flowering cabinet (1-3x PWM DO needed). (size and number to be determined)
- pressure sensors (I2C or SPI interface, also provide temperature and humidity data for statistics):
  - one for ambient pressure for reference. need to maintain lower pressure in cabinets to prevent air escape.
  - one for main outflow vent pressure as its activation feedback.
  - one for growing cabinet pressure, maintained by upper inflow cooling fan PWM.
  - one for flowering cabinet pressure, maintained by lower inflow cooling fans PWM.
- total gpio: 1x DO, 2-4x PWM DO, I2C or SPI interface.

### Watering:
- 1x water level sensor for water tank (1x AI needed).
- 1x water PH sensor for water tank (1x AI needed).
- 1x water temperature sensor for water tank (1x AI needed).
- 3x 24v water pumps, one for each pot.
- 3x 24v relays for pumps activation (3x DO needed).
- 3x soil moisture sensors (3x AI needed).
- 3x rain drop detector sensor as overflow detection (3x AI needed).
- total gpio: 3x DO and 9x AI channels.

### Total GPIO:
- 3 digital inputs: light detection sensors.
- 7 digital outputs: for relay activation (lights, fan and water pumps).
- 3 PWM outputs: for inlet fans speed control.
- 9 analog inputs: water tank sensors, moisture sensors and rain drop detectors.

### RPZ:
- 

### UPM:
- 2 pressure sensors via I2C, for growing cabinet and ambient pressures (pins 2 and 3).
- 1 PWM DO for upper inlet fan (pin 5).
- 1 digital input for growing cabinet light activation feedback (pin 6).
- 5 analog sensors for growing cabinet and water tank (pins A0-A3 and pin 10).
- 3 digital outputs for lights activation relays (pins 14, 15 and 16).

### LPM:
- 2 pressure sensors via I2C, for flowering cabinet and outflow fan pressures (pins 2 and 3).
- 2 PWM DO for lower inlet fans (pins 5 and 6).
- 2 digital inputs for growing cabinet lights activation feedback (pins 8 and 9).
- 4 analog sensors for flowering cabinet (pins A0-A3).
- 4 digital outputs for outflow vent and water pumps relays (pins 10, 14, 15 and 16).