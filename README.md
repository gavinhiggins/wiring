# Hero Robot Wiring Architecture & Diagram

Interactive, high-fidelity wiring diagram and connector reference for the **RoboMaster Hero Robot**, designed for GitHub Pages.

## Live Website
👉 **[https://gavinhiggins.github.io/wiring/](https://gavinhiggins.github.io/wiring/)**

---

## Key Architecture & Features

### 1. Interactive Edit Mode with Grid Snapping
- **✏️ Edit Mode Toggle**: Switch between View Mode (inspecting specs) and Edit Mode (arranging layout).
- **Component Dragging**: Click and drag any electronic module or motor. Connected wire endpoints automatically track with the component, staying cleanly attached.
- **Wire Dragging & Waypoint Editing**:
  - **Whole Wire**: Drag a wire's body to translate the entire run.
  - **Vertex Handles**: Draggable handles at each bend point that snap to the grid.
  - **Add Waypoints**: Click the green `+` handle at any segment midpoint to insert a new corner and begin dragging it immediately.
  - **Delete Waypoints**: Right-click on any vertex handle to remove that bend.
- **Grid Snapping**: Cycle grid snap between **20px**, **10px**, **5px**, and **Off**.
- **Persistence & Portability**:
  - **Auto-Save**: All changes are automatically persisted to your browser's `localStorage`.
  - **📋 Export / Import JSON**: Easily view, copy, or apply custom layout JSON configurations.
  - **↺ Reset Layout**: Instantly restore default factory positions at any time.

### 2. Slipring Boundary & Strict Upper / Lower Separation
- **Upper Robot (Gimbal / Turret / AI Compute)**: Located strictly above the slipring boundary.
  - **Kicker System**: M2006 Kicker motor with C610 ESC (Power & 4-pin encoder).
  - **Turret Power & CAN Breakouts**: Turret Breakout and upper CAN Breakout.
  - **Upper Drive / Launch**: **4 separate C620 ESCs** and **4 separate 3508 motors** connected to the Turret Breakout and CAN Breakout.
  - **Upper Controller & Sensors**: MCB Type C, SPI IMU, Jetson, Intel RealSense (USB), Buck 24V->5V converter, GM6020 Pitch motor, Speed Monitor & VTM.
  - **Upper Slipring Breakout**: Top connector interface directly over the slipring.
- **Slipring Interface**: 360° continuous rotational interface in the center.
- **Lower Robot (Chassis / Power / Drive / Referee)**: Located strictly below the slipring boundary.
  - **Lower Slipring Breakout**: Mirrors signals down into the chassis.
  - **Chassis Controller**: MCB Type A, Chassis SPI IMU, 7-pin OLED display.
  - **Yaw & Agitator**: Agitator C620 ESC + 3508 motor, Gimbal Yaw C620 ESC + 3508 motor.
  - **Chassis Drive System**: 4x C620 ESCs + 4x 3508 Wheel Motors driven over CAN 2 via the Chassis Breakout board and Current Sensor.
  - **Power System**: 6S LiPo Battery (XT60) feeding into the PMM (Power Management Module), splitting out via Y-Splits (Ammoboost & Gimbal), MCB-A, and Chassis Breakout.
  - **Referee Subsystem**: MCM, 4-plate daisy-chained Armor loop, Lightbar, and RFID reader.

### 3. Clean Single-Plane Bus Routing & Twisted Pairs
- Pure horizontal and vertical trace corridors with minimal turns and generous clearances.
- True sinusoidal twisted pairs for XT30 Power (Yellow/Gray), CAN 1 (White/Red), and CAN 2 (Red/Dark-Red).
- Text labels rendered on every wire along its longest segment with knockout backgrounds for clarity.

### 4. Interactive Modal & Flyout Specs
- In **View Mode**, click on any wire or key item to view complete specifications (connector type, wire gauge, crimp terminal, pin count, voltage ratings, communication protocol).
- Click on any board or motor to see all connected input/output harnesses.
- Mouse scroll to zoom, left-click drag to pan.
