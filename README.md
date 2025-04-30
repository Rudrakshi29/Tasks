# EV Start-Up Sequence Circuit

# PROJECT OVERVIEW:
This project implements a reliable and safe start-up controller for an Electric ATV. Built using an Arduino microcontroller, the circuit ensures that key safety conditions are met before enabling the low-voltage (LV) system. It includes push-button activation, sensor-based validation, buzzer signaling, and safety shutdown handling in accordance with ISO electrical safety standards.

# FEATURES:

* One-shot push button start-up with debounce protection
* 3-second buzzer alert} on successful system initialization
* Safety Checks:
    - Brake must be pressed
    - Vehicle must be in neutral
    - Charger must be disconnected
* TSAL (Traction System Active Light)} and \textbf{SSR (Solid State Relay)} control
* Serial monitoring of live voltage values for sensors and startup status
* Auto-reset on safety condition failure


# SYSTEM WIRING AND I/O:
- TSAL Indicator(D7):Lights up when system is active 
- SSR Output(D5):Activates LV circuit
- Buzzer(D3):Audible signal during startup
- Brake Sensor(A0):Reads brake voltage (pressed $>$ 2.0V) 
- Charging Detect(A2):Detects if charger is connected (HIGH $>$ 2.0V)
- Neutral Sensor(A4):Reads neutral gear position (HIGH $>$ 2.0V)
- Push Button(A5): Manual startup trigger (INPUT\_PULLUP)

# HOW IT WORKS:
* On power-up, a 500ms delay prevents false push-button detection.
* A valid push event, combined with all safety checks, initiates startup:
    * Buzzer sounds for 3 seconds.
    * TSAL and SSR are enabled.
* If charger is connected or neutral is disengaged, the system resets.
* All sensor voltages and statuses are logged to the Serial Monitor.

# SAMPLE SERIAL OUTPUT:
Brake: 2.18 | Chg: 0.10 | Neutral: 2.40 | Startup: 1

# PCB Layout and Schematic:
![WhatsApp Image 2025-04-16 at 21 18 50_f12887a6](https://github.com/user-attachments/assets/b28e34a6-12a6-4d0f-8eff-850f68d0d19f)
![WhatsApp Image 2025-04-16 at 21 18 50_e17aa9b4](https://github.com/user-attachments/assets/5a92abe0-3ed9-41ef-961f-9eb27a66a90c)


