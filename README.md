# Sentry Robot Wiring Architecture & Diagram

Interactive, high-fidelity wiring diagram and connector reference designed for GitHub Pages.

## Features
- **Accurate Architecture**: Chassis (PMM, MCB Type A, C620 ESCs, Encoders, IMU), Slip Ring interface, Turret/Gimbal (Turret Breakout, Pitch motor, C610/M2006 Kicker, Flywheels, MCB Type C), Edge AI (Jetson Orin Nano, Intel RealSense), and Referee Subsystems (MCM, Light Bar, 4x Armor Plates, Speed Monitor, VTM).
- **Color-Coded Wiring & Harness Types**:
  - **XT60 Battery Power**: Heavy-gauge DC line.
  - **XT30 Main Power**: Yellow & Gray twisted pair.
  - **JST 2-Pin CAN**: White & Red twisted pair.
  - **JST 4-Pin CAN + Low Power**: Dual twisted pairs (White/Red + Yellow/Gray).
  - **JST Armor Plate Cable**: Straight Orange.
  - **Ref Cable**: Straight Amber / Gold.
  - **Black Ref Cable**: Dark line to Light Bar.
  - **JST OLED Cable**: Straight Cyan line.
  - **Dupont IMU SPI Cables**: Straight Purple lines.
  - **USB-A to USB-C**: Straight Blue line for RealSense depth camera stream.
  - **3-Pin UART JST**: Straight Green lines for serial communication.
- **Interactive Inspection**:
  - Click on any wire or item in the **Key** to pop up a detailed specification window (wire gauge, crimp type, connector family, voltage/protocol).
  - Click on any module board to see all associated in/out harness links.
- **Navigation Controls**:
  - **Scroll**: Zoom in/out towards cursor.
  - **Left-Click Drag**: Smooth pan.
  - **Reset View / Fit All**: Quick camera reset buttons.

## GitHub Pages Deployment
This repository is configured so `index.html` can be served directly from GitHub Pages (`Settings` -> `Pages` -> Source: `main` branch, `/ (root)`).
