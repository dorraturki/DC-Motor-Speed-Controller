# DC-Motor-Speed-Controller

This repository contains the documentation for a **DC Motor Speed Controller**. The aim was to design, simulate, and build an electronic board capable of controlling the **speed and direction** of a DC motor.

## 🚀 Project Overview

A speed controller is an essential component in numerous applications, allowing for precise and efficient motor control. This project covers:

- Variable speed adjustment using PWM (Pulse Width Modulation)
- Direction control using an H-bridge
- Manual controls via push-buttons and potentiometer
- Integrated voltage regulation and safety features

---

## 🧰 Tools Used

- **PSpice**: for simulating circuit behavior
- **EAGLE**: for schematic capture and PCB routing
- **Oscilloscope & Multimeter**: for testing the real-world output signals

---

## 🔧 How It Works

### 1. Power Supply and Regulation

- Converts 220V AC to +12V and +24V DC using:
  - Bridge rectifier with 1N4004 diodes
  - Filtering capacitors (2200µF and 470µF)
  - 7812 voltage regulator
- Output provides clean, stable voltage for the whole circuit

### 2. PWM-Based Speed Control

- **NE555** in astable mode generates PWM signal
- PWM frequency determined by R and C values
- Signal is amplified by **LM358 op-amp**
- A sawtooth waveform is generated and compared via **LM393 comparator**
- Potentiometer allows manual speed adjustment

### 3. Direction Control Logic

- Implemented using **CD4011 NAND gates** and push buttons
- Allows toggling between clockwise and counter-clockwise rotation
- Outputs drive the **H-bridge**, which switches motor polarity

### 4. H-Bridge Motor Driver

- Controls both speed and direction
- Built from MOSFETs
- Accepts PWM input and logical signals to modulate power to motor

---

## 🖥️ Simulations

Each major block was simulated to verify functionality before hardware implementation.

| Block                 | Circuit Diagram                      | Signal Output                   |
|-----------------------|--------------------------------------|---------------------------------|
| Power Supply          | `Power Supply - Circuit.png`         | `Power Supply - Result.png`     |
| Square Wave Oscillator| `Square Wave - Circuit.png`          | `Square Wave - Result.png`      |
| Sawtooth Generator    | `Sawtooth Signal - Circuit.png`      | `Sawtooth Signal - Result.png`  |
| Comparator            | `Comparator - Circuit.png`           | `Comparator - Result.png`       |
| PWM Chopper           | `Chopper - Circuit.png`              | `Chopper - Result.png`          |

> All simulation visuals are found in the `simulations/` folder and demonstrate expected behavior at each test point (LSPs).

---

## 🧪 Final Implementation Steps

1. **Schematic Design** – Created in EAGLE
2. **Routing** – Careful manual layout of PCB with minimal crossovers
3. **Printing & Etching** – UV exposure and photogravure method
4. **Component Soldering** – Through-hole soldering for all parts
5. **Testing** – Using oscilloscope to confirm signal behavior at all test points

---

## 📸 Result

A fully functional PCB-based motor controller, tested and validated.

![Final Build](/Final_result.jpg) <!-- Replace with your actual photo path -->

---

