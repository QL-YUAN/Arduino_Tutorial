# Arduino Programming with C++ – Beginner Tutorial

## Table of Contents

1. [Introduction to Arduino](#1-introduction-to-arduino)
2. [Required Tools](#2-required-tools)
3. [Arduino Program Structure](#3-arduino-program-structure)
4. [Basic C++ Syntax](#4-basic-c-syntax)
5. [Digital Output (LED Control)](#5-digital-output-led-control)
6. [Digital Input (Button)](#6-digital-input-button)
7. [Control Structures](#7-control-structures)
8. [Functions](#8-functions)
9. [Serial Communication](#9-serial-communication)
10. [Analog Input](#10-analog-input)
11. [Good Programming Practices](#11-good-programming-practices)
12. [What to Learn Next](#12-what-to-learn-next)
13. [References](#13-references)



---

## 1. Introduction to Arduino

Arduino is an open-source electronics platform that combines:
- Hardware (microcontroller boards)
- Software (Arduino IDE)
- Programming using C++

It allows you to read inputs (sensors, buttons) and control outputs (LEDs, motors).

---

## 2. Required Tools

### Hardware
- Arduino Uno (or compatible board)
- USB cable

### Software
- Arduino IDE  
  https://www.arduino.cc/en/software

---

## 3. Arduino Program Structure

Every Arduino program (called a **sketch**) has two required functions:

```cpp
void setup() {
  // Runs once when the Arduino starts
}

void loop() {
  // Runs repeatedly forever
}
````

---

## 4. Basic C++ Syntax

### Comments

```cpp
// Single-line comment

/*
  Multi-line
  comment
*/
```

### Variables and Data Types

```cpp
int number = 10;
float voltage = 5.0;
bool isActive = true;
char letter = 'A';
```

### Constants

```cpp
const int ledPin = 13;
```

Constants cannot be changed after they are defined.

---

# FUNDAMENTAL ARDUINO CONCEPTS

---

## 5. Digital Output (LED Control)

Digital outputs can be either **HIGH (ON)** or **LOW (OFF)**.

```cpp
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);
  delay(1000);
  digitalWrite(ledPin, LOW);
  delay(1000);
}
```

---

## 6. Digital Input (Button)

Digital inputs read **HIGH** or **LOW** signals.

```cpp
int buttonPin = 2;
int ledPin = 13;

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int state = digitalRead(buttonPin);

  if (state == HIGH) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
```

---

## 7. Control Structures

### If / Else

```cpp
if (value > 100) {
  // Condition is true
} else {
  // Condition is false
}
```

### For Loop

```cpp
for (int i = 0; i < 5; i++) {
  digitalWrite(13, HIGH);
  delay(200);
  digitalWrite(13, LOW);
  delay(200);
}
```

---

## 8. Functions

Functions help organize and reuse code.

```cpp
void blinkLed(int pin, int time) {
  digitalWrite(pin, HIGH);
  delay(time);
  digitalWrite(pin, LOW);
  delay(time);
}

void loop() {
  blinkLed(13, 500);
}
```

---

## 9. Serial Communication

Serial communication is used for debugging.

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.println("Hello Arduino");
  delay(1000);
}
```

Open **Tools → Serial Monitor** in the Arduino IDE.

---

## 10. Analog Input

Analog inputs read values from **0 to 1023**.

```cpp
int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int value = analogRead(sensorPin);
  Serial.println(value);
  delay(500);
}
```

---

## 11. Good Programming Practices

* Use meaningful variable names
* Comment your code
* Break code into functions
* Avoid hard-coded values
* Keep code readable

---

## 12. What to Learn Next

* PWM and `analogWrite()`
* Sensors and modules
* Motors and servos
* Using Arduino libraries

---

## 13. References

* Arduino Reference: [https://www.arduino.cc/reference/en/](https://www.arduino.cc/reference/en/)
* Arduino IDE built-in examples




