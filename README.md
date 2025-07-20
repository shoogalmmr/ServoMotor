# Control 6 Servo Motors with Arduino UNO

This project demonstrates how to control **six servo motors** using an **Arduino UNO** and a **breadboard**, with detailed wiring instructions and test code.

## Table of Contents
[Components Required](https://github.com/shoogalmmr/ServoMotor?tab=readme-ov-file#components-required)

[Circuit Setup](https://github.com/shoogalmmr/ServoMotor?tab=readme-ov-file#circuit-setup)

[Wiring Diagram](https://github.com/shoogalmmr/ServoMotor?tab=readme-ov-file#wiring-diagram)

[Arduino Code](https://github.com/shoogalmmr/ServoMotor?tab=readme-ov-file#arduino-code)


## Components Required

| Component                  | Quantity |
|----------------------------|----------|
| Arduino UNO                | 1        |
| Servo Motor (SG90 or similar) | 6    |
| External Power Supply (recommended) | 1 |
| Jumper Wires               | As needed |
| Breadboard                 | 1        |

> **Important:** Avoid powering all six servo motors directly from the Arduino 5V pin. Use an external power source to prevent voltage drops or potential damage.

## Circuit Setup

### Signal Wire Connections

Connect the **signal wires** (usually orange) of each servo motor to the Arduino digital pins:

| Servo Motor | Arduino Pin |
|-------------|-------------|
| Servo 1     | D4          |
| Servo 2     | D5          |
| Servo 3     | D6          |
| Servo 4     | D7          |
| Servo 5     | D8          |
| Servo 6     | D9          |

### Power and Ground Connections

- Connect all **VCC (red)** wires of the servo motors to the positive rail of the breadboard. Then connect that rail to a 5V power source (external is preferred).
- Connect all **GND (black or brown)** wires of the servo motors to the negative rail of the breadboard.
- Connect the **GND of the Arduino** to the same negative rail to complete the common ground.

> Ensure the ground of the external power supply is connected to Arduino GND to avoid erratic behavior.

## Wiring Diagram

Below is the schematic for connecting six servo motors to the Arduino using a breadboard:


![Servo Motor Wiring Diagram](https://github.com/user-attachments/assets/64151c4c-8088-42fd-a7a8-48bb884773f3)

> Disclaimer About the Wiring Diagram Image :
The wiring diagram shown here is a hypothetical simulation setup intended for demonstration purposes.
In this simulation, the servo motors are powered directly from the Arduino’s 5V pin without an external power supply.
Important:
In a real hardware setup, powering multiple servos directly from the Arduino is not recommended due to current limitations.
An external power supply is required to ensure stable and safe operation.

## Arduino Code

This sketch moves all six servos from 45° to 135° and back in a loop.

```cpp
#include <Servo.h>

Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;
Servo servo6;

void setup() {
  servo1.attach(4);
  servo2.attach(5);
  servo3.attach(6);
  servo4.attach(7);
  servo5.attach(8);
  servo6.attach(9);
}

void loop() {
  testServos();
}

void testServos() {
  servo1.write(45);
  servo2.write(45);
  servo3.write(45);
  servo4.write(45);
  servo5.write(45);
  servo6.write(45);
  delay(1000);

  servo1.write(135);
  servo2.write(135);
  servo3.write(135);
  servo4.write(135);
  servo5.write(135);
  servo6.write(135);
  delay(1000);
}
```

## Important Note About Power Supply
In simulation environments, servo motors may work fine when powered directly from the Arduino’s 5V pin because the simulation does not account for real-world current and voltage limitations.

However, in real-world applications:

- It is essential to use an external power supply capable of providing sufficient current to all servo motors, especially when running multiple servos simultaneously.

- Failing to provide a separate and stable power source can lead to:

- Voltage drops,

- Unexpected resets of the Arduino,

- Potential damage to the Arduino or servos.

Therefore, always ensure to use an appropriate external power supply when implementing this project on actual hardware.
