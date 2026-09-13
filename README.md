# ESP32-Powered Bluetooth RC Robot Car

A 4-wheel drive (4WD) robotic car controlled wirelessly over Bluetooth using an ESP32 microcontroller, L298N Dual H-Bridge motor driver, and a customized Android smartphone application. The vehicle features differential steering drive, dynamic PWM motor speed regulation, interactive LED headlamps, and reverse indicator lights[cite: 8, 9, 10].

---

## Key Features

* **Wireless Bluetooth Control:** Uses ESP32's built-in Bluetooth stack (`BluetoothSerial`) to process commands directly from a mobile controller application.
* **4WD Differential Steering:** Independent directional control of left and right motor banks via dual H-bridge switching for Forward, Reverse, Spin-Left, and Spin-Right movements.
* **PWM Speed Control:** ESP32 hardware PWM (`ledc`) channels outputting up to 30 kHz frequency for smooth speed adjustment.
* **Integrated Auxiliary Lighting:** Programmed control for front headlights and rear reverse LEDs triggered dynamically by directional commands.
* **Dual Power Architecture:** Isolated logic and drive power paths preventing microcontroller resets during high motor current draws[cite: 9].

---

## Hardware Components

* ESP32 DOIT DevKit V1 Board
* L298N Dual H-Bridge Motor Driver Module
* 4x Plastic Gearbox (BO) DC Motors with Wheels[cite: 8, 9]
* 9V–12V DC Battery Pack (Motor Drive Power)[cite: 9]
* 5V USB Power Supply / Power Bank (ESP32 Logic Power)[cite: 9]
* Front/Rear LEDs (Headlights & Brake Lights)[cite: 10]
* Robot Chassis (Cardboard/Acrylic) & Jumper Wires[cite: 8]

---

## Pin & Hardware Configuration

| Component Pin | ESP32 Connection | Description |
| :--- | :--- | :--- |
| **L298N IN1** | GPIO 18 | Motor Bank 1 Direction Input[cite: 10] |
| **L298N IN2** | GPIO 5 | Motor Bank 1 Direction Input[cite: 10] |
| **L298N IN3** | GPIO 12 | Motor Bank 2 Direction Input[cite: 10] |
| **L298N IN4** | GPIO 14 | Motor Bank 2 Direction Input[cite: 10] |
| **L298N ENA** | GPIO 19 | PWM Channel 1 Speed Output[cite: 10] |
| **L298N ENB** | GPIO 27 | PWM Channel 2 Speed Output[cite: 10] |
| **Headlight LED** | GPIO 26 | Auxiliary Front Lighting Output[cite: 10] |
| **Rear/Brake LED** | GPIO 21 | Reverse/Rear Indicator LED Output[cite: 10] |

---

## Software Stack & Firmware

* **Platform:** Arduino IDE with ESP32 Board Manager[cite: 8]
* **Communication Protocol:** Serial over Bluetooth Classic (SPP)[cite: 8, 9, 10]
* **Core Libraries:** `BluetoothSerial.h`[cite: 10]
