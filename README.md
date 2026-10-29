# Hero Robot Wiring Architecture & Diagram

Interactive, high-fidelity wiring diagram and connector reference for the **RoboMaster Hero Robot**, designed for GitHub Pages.

## Key Architecture & Features

### 1. Slipring Boundary & Strict Upper / Lower Separation
- **Upper Robot (Gimbal / Turret / AI Compute)**: Located strictly above the slipring boundary.
  - **Kicker System**: M2006 Kicker motor with C610 ESC (Power & 4-pin encoder).
  - **Turret Power & CAN Breakouts**: Turret Breakout and upper CAN Breakout.
  - **Upper Drive / Launch**: **4x C620 ESCs** and **4x 3508 motors** connected to the Turret Breakout and CAN Breakout.
  - **Upper Controller & Sensors**: MCB Type C, SPI IMU, Jetson Orin Nano, Intel RealSense (USB A to C), Buck 24V->5V converter, GM6020 Pitch motor, Speed Monitor & VTM.
  - **Upper Slipring Breakout**: Serves as the top connector interface directly over the slipring.
- **Slipring Interface**: 360° continuous rotational interface in the center.
- **Lower Robot (Chassis / Power / Drive / Referee)**: Located strictly below the slipring boundary.
  - **Lower Slipring Breakout**: Mirrors signals down into the chassis.
  - **Chassis Controller**: MCB Type A, Chassis SPI IMU, 7-pin OLED display.
  - **Yaw & Agitator**: Agitator C620 ESC + 3508 motor, Gimbal Yaw C620 ESC + 3508 motor.
  - **Chassis Drive System**: 4x C620 ESCs + 4x 3508 Wheel Motors driven over CAN 2 via the Chassis Breakout board and Current Sensor.
  - **Power System**: 6S LiPo Battery (XT60) feeding into the PMM (Power Management Module), splitting out to X-Split, Y-Split, MCB-A, and Chassis Breakout.
  - **Referee Subsystem**: MCM, 4-plate daisy-chained Armor loop, Lightbar, and RFID reader.

### 2. PCB-Style Routing & Clean Wire Presentation
- Every wire route follows clean horizontal and vertical lines with 45° chamfers (ortho / 45° PCB trace styling).
- Wire crossings are kept to an absolute minimum with clean bus corridors.
- Twisted wires (XT30 Yellow/Gray, CAN 1 White/Red, CAN 2 Red/Dark-Red, CAN 4P dual twisted) render with clean, crisp interwoven sinusoidal styling.

### 3. Interactive Modal & Flyout Specs
- Click on any wire or key item to view complete specifications (connector type, wire gauge, crimp terminal, pin count, voltage ratings, communication protocol).
- Click on any board or motor to see all connected input/output harnesses.
- Mouse scroll to zoom, left-click drag to pan.
