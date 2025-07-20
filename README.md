# Control 6 Servo Motors with Arduino UNO

This project demonstrates how to control **six servo motors** using an **Arduino UNO** and a **breadboard**, with detailed wiring instructions and test code.

## Components Required

| Component                      | Quantity |
|-------------------------------|----------|
| Arduino UNO                   | 1        |
| Servo Motor (SG90 or similar) | 6        |
| Breadboard                    | 1        |
| Jumper Wires                  | As needed |
| External Power Supply *(optional but recommended)* | 1 |

> **Note:** If you're only testing with 1–2 servos briefly, powering them directly from the Arduino 5V pin may work.  
> However, when using 3 or more servos, it’s **strongly recommended** to use an external 5V power supply to ensure stable performance and prevent voltage drops.

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

- Connect all **VCC (red)** wires of the servo motors to the positive rail of the breadboard.
  - You can connect this rail to the **Arduino 5V pin** if you're using **1–2 servos** only.
  - For **3 or more servos**, it is **recommended** to use a separate 5V external power source.
- Connect all **GND (black or brown)** wires of the servo motors to the negative rail of the breadboard.
- Connect the **Arduino GND** to the same negative rail to complete the common ground.

> If using an external power supply, always connect its ground (GND) to the Arduino GND.


## Wiring Diagram

Below is the schematic for connecting six servo motors to the Arduino using a breadboard:

![Servo Motor Wiring Diagram](https://github.com/user-attachments/assets/d7919b17-ebce-401b-af00-f8cbfb3d608e)


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
