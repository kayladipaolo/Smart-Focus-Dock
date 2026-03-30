# Smart Focus Dock

## Overview
The Smart Focus Dock is an embedded system designed to reduce phone-related distractions during work or study sessions. The system encourages users to place their phone on a dock and remain focused for a selected period of time. If the phone is removed early, the session is marked as interrupted. If the phone remains for the full duration, the session is completed successfully.

This project was developed as part of **ECE 3375: Microprocessors & Microcomputers**.

---

## Features

- Automatic session start when phone is detected  
- Configurable focus duration (e.g., +1 hour, +30 minutes)  
- Real-time progress tracking  
- Detection of early phone removal  
- Clear feedback for:
  - Idle  
  - Active session  
  - Completed session  
  - Interrupted session  


---

## Prototype Implementation

The prototype was developed using the **DE10-Standard board** and focuses on validating the core system logic.

### Inputs:
- Pushbutton (simulates phone presence)

### Outputs:
- LEDs used as a progress indicator

### Key Characteristics:
- Polling-based input handling  
- Software delay timing  
- State machine architecture  

The prototype successfully demonstrates:
- State transitions  
- Timer behavior  
- Detection of interrupted sessions  

---

## Final System Design (Proposed)

The final system extends the prototype into a realistic embedded product.

### Hardware Components:

- **Microcontroller:** STM32  
- **Phone Detection:** IR proximity sensor  
- **User Input:** Buttons (e.g., +1 hour, +30 minutes)  
- **Display:** OLED (I2C or SPI)  
- **Optional:** Status LED or buzzer  

### Software Improvements:

- Interrupt-driven input handling  
- Hardware timer-based countdown  
- Expanded state machine (Idle, Setup, Active, Complete, Interrupted)  
- Modular software structure  

> **Note:** The final implementation code is included as a proposed design and was not tested on physical hardware.

---

## How It Works

1. User selects a focus duration  
2. System waits for phone placement  
3. When phone is detected → session begins  
4. Timer counts down in real time  
5. If phone is removed early → session interrupted  
6. If timer completes → session successful  

---

## Code Overview

The system is built around a **state machine**, which controls all behavior:

- `IDLE` → waiting for user input  
- `TIMER_SETUP` → user selects duration  
- `ACTIVE` → session running  
- `COMPLETE` → session finished  
- `INTERRUPTED` → phone removed early  

The final implementation introduces:
- Interrupts for input handling  
- Timer interrupts for accurate timing  
- Display updates for user feedback  

---

## Development Process

The system was developed through multiple iterations:

1. Basic state machine (Idle → Active)  
2. Timer + LED progress tracking  
3. Completion and interruption states  
4. Debugging (interrupted-state bug fix)  
5. Expansion to full system design (sensor, display, improved control)

---

## Authors

- Kayla DiPaolo  
- Bryce Nielsen  
- Jaemin Cho  

---

## Notes

- Prototype code is fully functional and was tested in the lab  
- Final system code is a conceptual implementation based on real embedded design practices  
- This project demonstrates the transition from a simple prototype to a more complete embedded system  


